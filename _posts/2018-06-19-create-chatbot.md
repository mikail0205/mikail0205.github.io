---
comments: true
title: Python으로 Telegram 봇 만들기(1)
description: 파이썬으로 챗봇 만들기
date: 2018-06-19
categories:
 - Python

tags:
 - Python
 - Telegram
 - Chatbot
---

## Bot father로 부터 내 봇 생성하기

Python으로 Telegram 챗봇을 만들어 보자. 먼저 텔레그램에서 @botfather을 검색한다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/search_botfather_img.PNG?raw=true)
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/whatbotcando.PNG?raw=true)
이런 메시지를 받게 되는데, /start 명령어를 입력하면 시작할 수 있다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/start.PNG?raw=true)

다음으로 /newbot 명령어를 통해 봇을 생성 가능하며, 봇 이름과 사용자 이름까지 입력하면 봇이 생성이 된다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/newbot.PNG?raw=true)
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/Inkedhyungin_test_bot_LI.jpg?raw=true)
그리고 위 이미지에 빨간 줄로 밑줄 그은 부분은 내가 만든 봇의 TOKEN으로 나중에 필요로 한다.

다음으로 봇의 프로필 사진을 바꾸고 싶다면 /setuserpic 명령어를 입력 후 원하는 사진을 올려주면 된다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/change_bot_image.PNG?raw=true)

그럼 최종적으로 이렇게 봇이 만들어지게 된다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/changed_profile_pic.PNG?raw=true)

## 봇 코드 구현

봇을 성공적으로 만들었으니 이제 다음단계로 넘어가보자. PyCharm을 통해 새 프로젝트를 만들어보자. [봇 api로는 python-telegram-bot을 사용했다.] [(참고주소)](https://python-telegram-bot.org/)

pip를 이용할 경우에는 이렇게 설치가 가능하다.

```
$pip install python-telegram-bot --upgrade
```

PyCharm에서 python-telegram-bot라이브러리를 임포트 해준다. 
(Ctrl + alt + s입력 한뒤 추가할 수 있다.)
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/import_library.PNG?raw=true)

프로젝트를 생성했으면

```
from telegram.ext import (Updater, CommandHandler, MessageHandler, Filters,)

token = 'Bot father에게 받은 bot token을 넣어준다.'
```
```
# 간단한 커맨드 두가지를 정의해보자
def start(bot, update):
    bot.send_message(chat_id=update.message.chat_id, text="봇 작동합니다.")

# 정해진 커맨드가 아닌 다른 명령을 받았을 때 출력할 메시지
def unknown(bot, update):
    bot.send_message(chat_id=update.message.chat_id, text="죄송하지만 그 명령어를 이해할 수 없습니다.")
```

```
# main문을 정의하고
def main():
    # Create Updater object and attach dispatcher to it
    updater = Updater(token)
    dp = updater.dispatcher
    print("Bot started")

    # Start the bot
    updater.start_polling()
    dp.add_handler(CommandHandler('start', start))
    dp.add_handler(MessageHandler(Filters.command, unknown))

    # Run the bot until you press Ctrl-C
    updater.idle()
    updater.stop()

if __name__ == '__main__':
    main()
```
>telegram.ext는 여러 클래스로 구성되어 있지만 가장 중요한 요소가 Updater와 Dispatcher인데 Updater클래스는 telegram에서 새 업데이트는 계속 가져와서 Dispatcher 클래스에 전달한다. Updater 오브젝트를 작성하면 Dispatcher가 작성되어 대기열과 함께 링크되며, Dispatcher에 등록된 핸들러에 따라 Updater에서 가져온 업데이트를 정렬하고 정의한 콜백 함수로 전달하는 다양한 유형의 핸들러를 등록할 수 있다.

코드를 잘 붙여넣었다면 아래와 같이 잘 작동할 것이다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/creation/start_command.PNG?raw=true)


## Release note
2018-06-19: First Update  

## References