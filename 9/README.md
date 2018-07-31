![poster](https://github.com/lacti/yyt/blob/master/9/poster.png)


# Summary

| 항목 | 내용 |
| --- | --- |
| 장소 | 서초 마제스타시티 타워1 7층 PUBG |
| 날짜 | 2018년 07월 14일 (토요일) |
| 시간 | 11시 30분부터 21시까지 |

[peter](https://github.com/hyunjong-lee)가 글쓰는 시점에 재직중인 회사에서 진행합니다. 회사 장소를 제공해주시는 관계자 분들께 감사의 말씀을 드립니다.


# Motivation

인생은 짧습니다. 잉여로웁시다.


# Objective

어떤 사소한 기능이라도 완성을 목표로 합니다.

- 재미와 기능의 완성 두 가지 모두를 잡기 쉽지 않겠지만 시간내에 완료하는 것을 목표로 합니다.
- 주제는 그 어떤 것도 가능합니다.


## Register

국산을 애용합시다. 아래 네이버 폼에 양식에 맞게 정보를 기입하시면 됩니다.

- [등록하기](http://naver.me/FDBsAcu9)


## Schedule

본 대회는 *2018년 7월 14일(토요일)* 오후 동안 진행됩니다. 늦으시는 분은 async하게 진행하시면 됩니다.

- **노트북은 반드시 지참해야합니다.**
- 대회 당일 (7월 14일) 이전부터 구현하시는 것을 적극적으로 추천합니다.

| 시간 | 내용 |
| --- | --- |
| 11시 30분-12시 | 소개 & 노래 합창 |
| 12시-13시 | 점심 식사 |
| 13시-20시 | 대회 진행 |
| 20시-21시 | 저녁 식사, 결과 공유, 평가 |


## Team

잉여톤 8회에 [lacti](https://github.com/lacti) 님께서 언급하셨듯이 _미리 구성해놓고 와서 진행하는 편을 추천합니다. 매번 stateless한 PoC를 진행하는 것도 물론 재미있는 일이지만, 이제 8회차나 진행되었기 때문에 보다 결과를 남길 수 있는 무언가를 해보는 것도 의미가 있지 않을까 생각합니다._

이하 [lacti](https://github.com/lacti) 님 전언

_물론 가볍게 즐기는 것도 매우 중요하기 때문에, 와서 재미있어 보이는 곳에 견학이나 참가를 하는 것도 좋고, 1인 팀으로 진행하는 것도 아주 좋습니다.
원하는 가장 편한 방법을 택해서 진행하면 됩니다._

---

# Result
## Space Battle (http://bash.style)

![Space Battle](https://i.ytimg.com/vi/ap27AwqOwsc/maxresdefault.jpg)
<_인게임으로 계획된 머릿속의 이미지_>

- 시작전 포부: 나 이런 사람이야
- 목표: 어릴때 열심히 했던 Unity3D의 경험을 그냥 묵히기 아쉬워서 시작한 엔진만들기, (_미완성된_) 엔진은 있으니까 게임을 하나라도 제대로 만들어보자.
- 계획된 기능
  - 스플래시 스크린
  - 아웃게임 (리더보드, 게임시작 버튼, 현재 접속자 수, 방 고르기, 닉네임 고르기)
  - 인게임
  - 결과창
  - 저작자 소개 (like *star wars ending credit* )
- 사용된 기술: HTML5 Canvas, Javascript, WebSocket
- 아쉬운점: 시간이 상당히 많다고 자만했지만 2시간만에 체력 고갈로, 오히려 시간이 부족하여 alert로 결과창을 대신함.... (쩝)
- 다음을 기약하며: slither.io처럼 게임 출시 할 때 까지 완성도를 높이겠다.

## ICBM ([link](https://github.com/dplusic/ideal-computing-breaking-machine/releases/tag/yyt9))

* 목표
  * 기존의 ICBM에 GameLift를 이식하는 작업을 진행
* 진행
  * GameSession의 생성, Player의 진입, GameSession의 종료의 Life Cycle을 구현
  * 코드가 더 필요하지는 않겠지만 Instance의 Scaling을 설정하지는 못함
* 후기
  * GameLift로 Scalable한 Relay Server를 구현하고 나니, MQ Cluster만으로 할 수 있다라는 [lacti](https://github.com/lacti)님의 제안보다 나은 것이 없는 상황이 되었으나, Relay Server를 직접 코드 레벨에서 Customize할 수 있다는 점을 주안점으로 삼고 GameLift를 이용하는 방향을 유지해볼 생각임

## TinyGBT ( https://github.com/lancifollia/tinygbt )

[Gradient Boosted Tree 알고리즘](https://xgboost.readthedocs.io/en/latest/tutorials/model.html)을 python으로 쉽게 짜봤습니다.
기존 구현체인 [LightGBM](https://github.com/Microsoft/LightGBM)과 간단하게 정확도를 비교해봤는데, (속도는 엄청 느리지만) 비슷한 parameter 셋팅에서 비슷한 에러(RMSE)가 나왔습니다.

## move move move ( https://github.com/noasax/yyt9 )
![poster](https://i.imgur.com/Zz0TgGx.png)
* 나보다 작으면 지워버리고 크면 도망가라!
  * 움직일수록 크기가 커집니다
  * 크기가 커질수록 속도는 느립니다
  * 충돌시 작은(약한)자는 사라집니다
* 목적
  * 계속 움직이는 잉여력 넘치는 자가 승리하는 게임
* 개발
  * node js 서버에서 모든 상태를 통제하고 web socket과 canvas를 사용합니다.
* 문제점/개선점
  * 한 점이 커지면 답이 없어짐(하지만 누군가 한명은 커짐)
  * 맵을 더 크게, 클라이언트에 맞게 보여주는 기능

## 가즈아 (gazzzza)

* [지난 8회 가즈아](https://github.com/lacti/yyt/tree/master/8#%EA%B0%80%EC%A6%88%EC%95%84-httpsgithubcomhyunjong-leegazzzza) 를 이어하며 완성도를 높이기 위해 작업
![Gazzzza](https://github.com/lacti/yyt/blob/master/9/images/gazzzza.png)
<_일단은 대충 완성된 가즈아의 화면_>

* 기존에 없던 기능 추가
  * MP 개념을 추가하여 항상 방어상태가 되지 않도록 처리
  * 각 턴에 MP가 +3이 되도록 추가
* 이번 9회차의 목표는 완성 (COMPLETION) 이었던 만큼 팀을 이루어 작업 진행
  * 기획의 완성도
    * 지난번 게임은 기획적 완성도가 낮아 재미가 없었다고 판단하여 알고 있는 기획자 2명과 논의한 피드백을 바탕으로 구현 목표를 세움
  * 클라의 완성도
    * 장고로 대충 만든 웹사이트말고 제대로 된 클라이언트가 나오길 원해서 김거엽님과 팀을 이루어 작업
* 개인 소감
  * 현종
    * 오랜만에 집중도 있게 개발할 수 있어서 의미있는 모임이었다고 판단
    * 기획을 넣으면 재미있지 않을까 했지만 핵노잼
    * 김거엽과 팀을 이뤄 작업하다보니 Gaming on AWS 1회때의 추억이 떠오름
    * 완성도를 높이면 어떻게 1등할 수 있지 않을까 했지만 굇수들의 출현으로 무산
  * 거엽
    * 'C'(땅) / 'C++'(불) / 'Lua'(바람) / 'HTML5 & CSS'(물) / '대리님'(마음) 다섯 가지 힘을 하나로 모으는 것은 역시 쉬운 일이 아니지만, 어려운만큼 그 보람 또한 크단 사실을 재확인했다
    * 가즈아의 게임 플레이 메커니즘은 완전히 정적이긴 하나, 연출이라도 다소 역동적이었으면 게임적 재미가 있었을 것이라 생각한다 (문명 시리즈가 대표적인 예)
    * 다음에는 아티스트를 꼬셔서 같은 팀으로 만들어보면 좋겠다
    

## 총론
* 매우 유익한 9회차 모임
* 멤버가 조금 더 늘어나면 공개 모집으로 진행해도 재밌을 듯
* 현재까지 진행된 잉여톤을 AWS 측에 공유해서 꾸준히 진행하고 있음을 어필해도 괜찮아보임
* 최종 스탠딩
![Final Standing](https://github.com/lacti/yyt/blob/master/9/images/final_standing.jpg)


## 참고

대체 이것이 무엇인지에 대한 궁금증은 [README](https://github.com/lacti/yyt/blob/master/README.md)에서 어느 정도 해소가 될 것으로 기대합니다.
만약 이 행사에 처음 접근했다면, 위 글도 참고 부탁 드립니다.
