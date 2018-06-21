---
comments: true
title: Python으로 Telegram 봇 만들기(4) - 네이버 실시간 인기검색어 받아오기
description: 네이버 메인 페이지에서 실시간 인기검색어를 받아오도록 하자
date: 2018-06-21
categories:
 - Python

tags:
 - Python
 - Telegram
 - Chatbot
---

## 네이버 인기검색어
우선 네이버 홈페이지로 접속을 해본다. (https://www.naver.com/)
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/part4/naver_main.png?raw=true)

네이버 검색어를 크롤링 해보도록 하자. 찾아보니 `area_hotkeyword PM_CL_realtimekeyword_rolling_base` `div`안에 `ul`이 있고 그 안에 `ah_item`라는 이름으로 `li`들이 있으며 또 그 안에 `ah_r`인 순위 클래스와 `ah_k` 키워드 클래스가 들어있다.

## 코드
`naver_issues.py`
``` python
import requests
from bs4 import BeautifulSoup

def issue(self, update):
    session = requests.Session()
    addr = 'https://www.naver.com/'
    self.addr = addr
    req = session.get(self.addr)
    soup = BeautifulSoup(req.text, 'html.parser')

    for item in soup.find("div", {"class": "ah_roll_area PM_CL_realtimeKeyword_rolling"}).findAll("li", {
        "class": "ah_item"}):
        count = item.find("span", {"class": "ah_r"}).getText()
        title = item.find("span", {"class": "ah_k"}).getText()
        update.message.reply_text("{0}위는 '{1}'입니다".format(count, title))

```
`main.py`
``` python
# 메인에 추가해준다.
from modules.naver_issues import issue
dp.add_handler(CommandHandler('인기검색', issue))
```
보통은 이런 식으로 반복문을 많이 사용하지만, 반복문을 사용하면 메신저에서는 그만큼 메시지 박스가 생성이 되는데 한두 개면 괜찮을지 모르지만 계속 늘어나면 보기 불편하다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/part4/for.PNG?raw=true)


``` python
    table = soup.find(class_='ah_l')
    t_ary = list(table.stripped_strings)
    update.message.reply_text('실시간 네이버 인기검색어\n'
                              + t_ary[0] + '위: ' + t_ary[1] + '\n'
                              + t_ary[2] + '위: ' + t_ary[3] + '\n'
                              + t_ary[4] + '위: ' + t_ary[5] + '\n'
                              + t_ary[6] + '위: ' + t_ary[7] + '\n'
                              + t_ary[8] + '위: ' + t_ary[9] + '\n'
                              )

```
그래서 조금 귀찮은 일이지만, 이런 식으로 하나의 메시지 박스에 출력을 해주면 보기엔 좋다고 생각하여 코드를 수정하였다.
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/part4/onetime.PNG?raw=true)


## Release note
2018-06-21: First Upload
## References
https://appear.github.io/2017/12/03/Python/python-13/