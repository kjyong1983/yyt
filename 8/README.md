![poster](https://github.com/lacti/yyt/blob/master/8/poster.png)

# Summary

| 항목 | 내용 |
| --- | --- |
| 장소 | 서초 마제스타시티 타워2 9층 보이저엑스 |
| 날짜 | 2018년 06월 02일 (토요일) |
| 시간 | 12시부터 20+a시까지 |

[lacti](https://github.com/lacti)의 회사에서 진행합니다. 회사 장소를 제공해주시는 관계자 분들께 감사의 말씀을 드립니다.

# Motivation

회사를 다니거나 운영하거나 아니면 놀게 되면서, 생활에 찌들어 저 멀리 어딘가 사라지고 있는 코딩 감성(잉여력)을 회복하기 위해 잉여톤을 열어봅니다.

# Detail

다음을 만족하는 게임을 개발합니다.

- 시스템의 자원을 최소한으로 사용할 수 있어야 합니다. 즉, 최대한 비용을 지불하지 않고 구축할 수 있는 시스템을 설계해봅시다.
- 여러 사람이 함께 플레이할 수 있어야 합니다.
- 말라가는 코딩 감성(잉여력)을 회복할 수 있어야 합니다.

게임적 재미는 옵션 사항입니다. 단, 재미를 목표로 하지 않았다면 목표로 했던 그 요소에 대해 참가자들에게 설명을 해야합니다.

다들 아시겠지만, 이후 참가자들은 위 기준에 따라 적절히 평가하여 *누가 가장 잉여력을 많이 회복시켜주는지* 순위를 매기게 됩니다.

노트북은 반드시 지참해야합니다.

## Schedule

본 대회는 *2018년 6월 2일(토요일)* 오후 동안 진행됩니다. 기다리는 다른 분들을 위하여 최대한 시간을 준수해주시기를 부탁 드리고 싶습니다.

| 시간 | 내용 |
| --- | --- |
| 12시-13시 | 점심 식사 |
| 13시-20시 | 대회 진행 |
| 20시-20+a시 | 저녁 식사, 결과 공유, 평가 |


## Team

미리 구성해놓고 와서 진행하는 편을 추천합니다. 매번 stateless한 PoC를 진행하는 것도 물론 재미있는 일이지만, 이제 8회차나 진행되었기 때문에 보다 결과를 남길 수 있는 무언가를 해보는 것도 의미가 있지 않을까 생각합니다.
때문에 현재 진행 중인 작업을 적당히 공유해서 뜻이 맞는 사람을 구하고, 그것에 대한 잉여롭고 폭발적인 진행을 위해 대회를 참가하는 것이 보다 효율적이고 재미있는 대회 진행을 즐길 수 있는 방법이 아닐까 생각합니다.

물론 가볍게 즐기는 것도 매우 중요하기 때문에, 와서 재미있어 보이는 곳에 견학이나 참가를 하는 것도 좋고, 1인 팀으로 진행하는 것도 아주 좋습니다.

원하는 가장 편한 방법을 택해서 진행하면 됩니다.

---

# Result

## 가즈아 (https://github.com/hyunjong-lee/gazzzza)

- 6명이 즐기는 게임
- 각자 HP 100이 있으며 칼 혹은 펜으로 특정 상대를 공격할 수 있음
- 칼은 20의 데미지, 펜은 10의 데미지를 입힘, 방어는 무적 방어
- 이 때, 펜은 칼보다 강하므로 1:1 맞대결 상황에서는 펜이 공격이 들어가고 칼은 무효화
- 무적 방어에 대한 기획은 보강이 필요하며, 칼과 펜의 상성에 대해 좀 더 연구하면 재미를 추구할 수 있을 것으로 보임
- 웹으로 뚝딱뚝딱 만들었는데 제대로 된 클라이언트로 작업이 필요해 보임
- 아래는 실행화면

| enter | play | admin |
|-------|------|-------|
| ![enter](https://github.com/lacti/yyt/blob/master/8/images/enter.png) | ![play](https://github.com/lacti/yyt/blob/master/8/images/play.png) | ![admin](https://github.com/lacti/yyt/blob/master/8/images/admin.png) |

---

## 운송왕 이운송 (https://github.com/lache/lo)

- 초기 목표: 게임 내 한글 채팅 기능 추가
- 문제점: 게임 실행되는 동안 내내 IME 사용 불가 상태로, 한영 변환이 불가함
- 관찰1: 빈 Win32 프로그램 생성 후 IME 사용이 정상적으로 가능함을 확인
- 관찰2: 빈 GLFW 프로그램 생성 후 IME 사용이 정상적으로 가능함을 확인
- 시도1: GLFW 최신 업그레이드
- 시도1 결과: 문제가 해결되는 컴퓨터가 있고, 해결되지 않는 컴퓨터가 있음...
- 시도2: 프로젝트 초기화 단계의 처리를 한줄씩 삭제해나가며 점점 빈 GLFW 프로그램으로 바꿔봄
- 시도2 결과: CoInitializeEx() 두 번째 인자를 'COINIT_MULTITHREADED'에서 'COINIT_APARTMENTTHREADED'로 바꾸니 문제 해결됨
- 총평: 왜 해결됐는지는 모르겠지만 여튼 해결됐음
- 후기: 간만의 삽질은 달콤했다......
- ![ttlchat](https://github.com/lacti/yyt/blob/master/8/images/ttlchat.png)

---

## network two tracks (https://github.com/lacti/ntt)

![ntt](https://github.com/lacti/yyt/blob/master/8/images/ntt_result.png)

### network model

transactional한 요청을 처리하는 rpc (over tcp)와 broadcasting을 담당하는 udp를 적절히 사용하여 간단한 이동 동기화 및 거래 정도가 수행되는 게임을 만드는 것이 목표였습니다. 하지만,

- grpc webclient가 생각보다 잘 동작하지 않았고, (서버를 go로 만들어야 했습니다.)
- web browser에서 udp 통신이 생각보다 간단하지 않았습니다. (webRTC로 어떻게 하겠다는 spec만 봤습니다.)

때문에 이걸로 충분히 삽질하다가 3시간만에 포기하고 그냥 `socket.io`를 사용해서 위치 동기화만 구현했습니다.

### deployment

web으로 만들었기 때문에 배포는 상대적으로 간단합니다.

- [front-end](https://github.com/lacti/ntt/tree/master/web)의 pack 결과를 [server](https://github.com/lacti/ntt/tree/master/server)가 serving하고 이를 [docker](https://github.com/lacti/ntt/blob/master/Dockerfile)로 묶어서 [docker-compose](https://github.com/lacti/ntt/blob/master/docker-compose.yml)로 관리할 수 있도록 합니다.
- 이에 대한 [electron client](https://github.com/lacti/ntt/tree/master/desktop)를 만들고 이를 [CI에서 배포하도록](https://github.com/lacti/ntt/blob/master/.travis.yml) 설정합니다. 단, wine 환경이 필요하므로 이에 대한 [docker image](https://github.com/lacti/docker-node-env)를 만들어둡니다.

### 후기

와서 기술 실험을 하는 것도 재미있는 일이지만, 짧은 시간 내에 기술 탐구와 구현을 모두 수행하기는 쉽지 않습니다. 따라서 행사 전 어느 정도 기술의 PoC를 수행해놓고 당일에는 그 기술을 엮어서 결과물을 만들어내는 것에 더 집중하면 조금 더 재미있는 결과를 만들어낼 수 있지 않을까 기대하고 있습니다.

---

## BobRank (https://github.com/doodoori2/bobrank/blob/master/README.md)

### 구현 목표

- 게임 등에서 주로 사용하는 실시간 랭킹 추정에 대한 알고리즘에 대한 PoC
- 현재 점수 분포에서 특정 점수의 랭킹 백분위를 추적함
- 전체 데이터가 아닌, 구간 데이터만을 사용하여 랭킹 추정을 함
- 점수 추가 / 변경을 실시간으로 반영함
- 구간의 점수 기준이 입력되는 데이터 값의 변화에 따라 유기적으로 대응함

---

대체 이것이 무엇인지에 대한 궁금증은 [README](https://github.com/lacti/yyt/blob/master/README.md)에서 어느 정도 해소가 될 것으로 기대합니다.
만약 이 행사에 처음 접근했다면, 위 글도 참고 부탁 드립니다.
