---
comments: true
title: Python으로 Telegram 봇 만들기(3) - 네이버 영화순위 받아오기
description: 네이버영화 페이지에서 순위를 받아오자
date: 2018-06-21
categories:
 - Python

tags:
 - Python
 - Telegram
 - Chatbot
---

## 네이버 영화
네이버 영화 메인에 방문하면 현재 상영 중인 영화 순위가 나온다.(http://movie.naver.com/movie/running/current.nhn)
![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/part3/naver_movie.png?raw=true)
F12를 눌러서 찾고자 하는 정보를 찾아 따라 내려가다 보면 저렇게 영화 제목과 별점 등을 찾을 수 있다. 여기서는 제목과 해당 영화의 링크만을 받아와서 출력할 것이다.

## 코드
`naver_movie_rank.py`
``` python
from bs4 import BeautifulSoup
import requests
# 지난번과 마찬가지로 웹에서 정보를 받아오기 위해 필요한 것들을 import해준다.

def show_ranklist(self, update):
    session = requests.Session()
    addr = 'http://movie.naver.com/movie/running/current.nhn'

    self.addr = addr
    req = session.get(self.addr)
    soup = BeautifulSoup(req.text, "html.parser")
    titles = soup.find_all('dl', class_='lst_dsc')

    rank = 1
    for title in titles:
        update.message.reply_text(str(rank) + '위: ' + title.find('a').text + "\n"
                                  + "Link : " + addr + title.find('a')['href'] + "\n"
                                  )
        rank += 1
        if (rank == 6):
            break
```
지난번에는 반복문을 쓰지 않고 했었는데, 반복문을 사용하면 이렇게 메시지 박스가 여러 개가 등장하기 때문이다.

`main.py`
``` python
from modules.naver_movie_rank import show_ranklist
dp.add_handler(CommandHandler('영화순위', show_ranklist))
```

처음 코드를 작성할 때는 영화 제목뿐 아니라 각종 평점과 장르, 상영시간 등 많은 정보를 받아오려고 했었지만, 그냥 순위만 받아와서 링크를 달아주고 보는 사람이 관심 있는 영화 링크 따라가서 보는 게 더 좋지 않을까 싶어서 제목과 링크 두 가지만 받아왔다.

![](https://github.com/mikail0205/mikail0205.github.io/blob/master/assets/images/2018/telegrambot/part3/show_movie_rank.PNG?raw=true)

## Release note
2018-06-21: First Upload
## References