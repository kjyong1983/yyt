![poster](https://github.com/lacti/yyt/blob/master/10/yyt_10.jpg)

> 당신의 잉여력, 지금 소중히 보관하고 있습니까?

# Summary

| 항목 | 내용 |
| --- | --- |
| 장소 | 개롱 |
| 날짜 | 2018년 9월 8일(토요일) |
| 시간 | 12시부터 20시까지 |

# Motivation

[Aurora Serverless](https://aws.amazon.com/ko/blogs/aws/aurora-serverless-ga/)가 출시 되었습니다. 이로써 대부분의 예전 서버 모델을 서버리스로 옮기는데 큰 무리가 없게 되었다고 봐도 과언이 아닙니다.

~~하지만 서버리스가 어떤 점이 더 나은지 고민이 부족한 것도 사실입니다. 따라서~~ 기존 모델로 서버-클라이언트 구조의 서비스를 구축하고, 서버리스가 문제 해결에 어떻게 도움을 줄 수 있을 지 고민해봅시다.

# Detail

다음을 만족하는 시스템을 개발합니다.

- 서버-클라이언트 모델이어야 합니다.
- 서버리스를 사용하지 않아야 합니다.
- 확장성은 생각만 하고 구현할 필요는 없습니다.
- **참가자들의 서버 사이에 서로 통신하여 동작할 수 있는 적어도 한 개 이상의 API point를 설계**해야 합니다.
  - 때문에 개별/팀 참가자들은 자체적으로도 의미있는 수준의 서비스를 작성해야 하며,
  - 뿐만 아니라 다른 개별/팀 참가자들과도 의미있는 수준의 통신을 수행해야 합니다.
- 시스템은 게임이어도 좋습니다.

서버리스는 비용이나 확장성 측면에서 기존 개발 방법보다 더 유리하다고 알려져 있습니다. 그렇지만 이 구조는 필연적으로 microservice 구조를 따라가게 되고, 이 때문에 monolithic 구조와 비교했을 때 구현과 유지보수 비용 등이 증가한다고 알려져 있습니다.

따라서 본 대회에서는 최대한 서로 복잡하게 연동된 monolithic 서버 구조를 개발하고, 시스템의 유연성과 확장성 관점에서 서버리스가 문제를 어디까지 해결해 줄 수 있을 지 토론하고자 합니다.

서로 네트워크 통신을 진행해야 하는데 개롱 site의 네트워크는 상당히 취약합니다. 마침 monolithic 서버 구조를 개발하므로, 개별/팀 참가자들마다 _aws m5.large ec2 instance_ 를 하나씩 지급할 예정입니다. 또한 개롱 site에는 적절한 presentation 도구가 없으므로, 적어도 *HDMI 단자를 지원하는 노트북* 혹은 그에 준하는 도구를 직접 준비해오시는 것을 권장합니다.

## Schedule

본 대회는 *9월 8일(토요일)* 오후 동안 진행됩니다. 기다리는 다른 분들을 위하여 최대한 시간을 준수해주시기를 부탁 드리고 싶습니다.

| 시간 | 내용 |
| --- | --- |
| 12시-13시 | 점심 식사 |
| 13시-18시 | 대회 진행 |
| 18시-19시 | 결과 공유 |
| 19시-20시 | 저녁 식사, 토론 |

## Participation

공간이 협소하기 때문에 on site 모임은 최대 10명 정도의 인원으로 제한하게 되는 점 양해 부탁 드립니다.  
참가를 원한다면 [Google Form](https://goo.gl/forms/3PJIoHBP3xKj3phN2)에 이름과 연락처를 남겨주세요. 장소가 대단히 private한 관계로 이 쪽으로는 공개하지 않는 점도 양해 부탁 드립니다.

**참가 신청은 9월 3일까지 받으므로 그 전까지 신청 부탁 드립니다.**

## Team

- 미리 팀을 구성해서 같이 신청을 해도 좋고
- 와서 팀을 구성해서 진행해도 좋고
- 아니면 1인 팀으로 진행해도 좋습니다.

원하는 가장 편한 방법을 택해서 진행하면 됩니다.

## Result

## GyroPlane (Airplane팀)

* https://github.com/kjyong1983/GyroPlane
![GyroPlane](https://github.com/lacti/yyt/blob/master/10/images/gyroplane.png)
<_게임을 시작하자마자 추락을 시작하는 시점에서의 마지막 정상적인 카메라 앵글을 순간포착한 장면_>

* 게임의 큰 틀은 잡힌 상태로 시작
* 휴대폰 자이로센서를 이용해 각자의 1인칭시점 비행기를 조종하고, 서로를 격추시켜 승리하는 게임
* 자이로센서가 입력이므로 도그파이트 상황에서 참여자가 모두 몸을 이리저리 비틀어야하는 점이 백미
* 네트워크 미들웨어로 Photon을 사용
* 클라이언트 구현 노트
  * 위에서 언급한 것처럼 빠른 시간내에 구현을 위해 자이로센서를 이용한 조작체계를 미리 잡아옴.
  * 서버 프로그래밍을 못하는 관계로 네트워킹은 모두 Photon에게 맡김
  * 유저가 게임을 켜면 자동으로 방으로 들어오고, 방이 없으면 하나 만들고 들어가서 전투하는 방식을 모두 Photon이 해줌
  * 간단하게 비행기의 가속과 감속, 총알 발사의 기능만 구현
  * 유니티의 자이로 센서는 Quaternion 값을 받아 쓰기 때문에 회전값을 파악하는데 머리가 아프다
* 서버 구현 노트
  * 다른 팀에서 사용할 공개 API로 두 가지를 계획: (1) 현재 플레이어 목록 및 점수, (2) 미사일 생성
  * Node.js를 이용해 프론트엔드 서버를 구축할 계획
  * Node.js - Photon 바인딩 라이브러리로 [photon-node](https://www.npmjs.com/package/photon-node)를 후보에 뒀으나, 여기의 photon은 그 Photon이 아닌 것으로 판명
  * 장시간 고민하다, 서버 역시 Unity로 작성하면 모든 문제가 눈녹듯이 사라진다는 사실이 번개처럼 뒷통수를 내려침
  * 초기 지급받았던 Ubuntu EC2 머신을 황급히 Windows EC2 머신으로 교체
  * 프론트엔드(HTTP 서버) - Unity - Photon Unity Network (PUN) 구조의 스택을 구현
  * 프론트엔드(HTTP 서버)는 [uniwebserver](https://github.com/simonwittber/uniwebserver)의 것을 사용
  * 모든 구현은 C#
  * Photon 미들웨어를 배워서 쓸 시간이 없어서, 본 '서버'가 '서버'의 권한을 가지게 하는 방법을 제대로 배우지 못함
  * 즉, 다른 유저의 점수를 조회한다든지, 새로운 오브젝트(미사일)를 생성한다든지 하는 서버 권한의 작업을 어떻게 구현해야 할지 막막
  * 그냥 '권한'이란 개념을 없애고 보안상 문제가 아주 크겠지만, 모든 유저의 데이터와 미사일 생성 등을 공개 권한으로 하여, 문제 자체를 없애버림
  * 두 가지 API가 최종적으로 만들어짐
    * `/players`, `/fireBullet`
  * Windows 서버에 Unity 에디터를 설치하는 흔히 경험 못할 진귀한 일도 진행
  * 개발 과정 중, 동운의 DDOS 공격으로 개발 머신 블루스크린 경험
* 개인 소감
  * 거엽
    * 서버와 클라이언트가 모두 Unity라는 동일 엔진 위에서 돌아가니 만사가 편함
    * Photon 라이브러리는 무척 간단하게 쓸 수 있도록 잘 만들어짐
    * 다만, 너무 쉽게 만들어 둬서 그런지는 몰라도 첫 느낌은 성능상 오버헤드가 느껴짐 (실시간 동기화 랙)
    * 최종 결과물에 버그가 발생해서 모두가 함께 플레이해보지 못한 점은 무척 아쉬운 부분
  * 진용
    * 개발을 하는데 있어 유니티 PC 에디터와 안드로이드 플랫폼별로 작동이 제대로 먹히지 않았고
    * 개발용 디버그를 잘못 건드리는 바람에 결과물에 자이로 센서가 먹히지 않았던 부분은 매우 아쉬움
    * Photon을 처음 써봤지만 무척 쓰기 쉬웠다. 다만 아무리 쉽다고 해도 총알을 쏘는 것과 그것을 동기화하는 일은 그래도 어려움
    * 총알의 폭발 이펙트를 너무 무거운 것으로 넣어서 총알만 쏘면 폰이 멈추려고 함. 최적화가 필요함
    * 시간과 예산 부족으로 닉네임을 넣어서 화면에 띄우는 것과 RNG의 동기화에 실패함.

## https://github.com/dplusic/friendly-winner/tree/yyt10

---

대체 이것이 무엇인지에 대한 궁금증은 [README](https://github.com/lacti/yyt/blob/master/README.md)에서 어느 정도 해소가 될 것으로 기대합니다.
만약 이 행사에 처음 접근했다면, 위 글도 참고 부탁 드립니다.
