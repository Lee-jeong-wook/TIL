# TCP/IP 흐름제어, 혼잡제어
##### TCP 통신이란
- 네트워크 통신에서 신뢰적인 연결방식
- TCP는 기본적으로 unreliable network에서 reliable 데이터로 보장할 수 있도록 하는 프로토콜
- TCP는 network congestion avoidance 알고리즘 사용
> 개별 소켓에 패킷의 왕복 시간을 분석하는 알고리즘
##### Reliable network를 보장한다는 것은 4가지 문제 존재
1. 손실: packet이 손실될 수 있음
2. 순서 바뀜: packet의 순서가 바뀜
3. Congestion: 네트워크 혼잡
4. Overload: Receiver가 overload 되는 문제
##### 흐름/혼잡 제어란
- 흐름제어
> - 송신측과 수신측의 데이터처리속도가 차이나지 않게 해결하는 기법
> - Flow control은 receiver가 packet을 지나치게 받지 않도록 조절하는 것
> - 기본개념은 receiver가 sender에게 현재 자신의 상태를 feedback 하는 것
##### 전송의 전체 과정
- Application layer: sender application layer가 socket에 data를 씀
- Transport layer: data를 segment에 감싼다. 그리고 network layer에 넘김
- 아랫단에서 receiving node로 전송이 되는데 이 때 sender에 send buffer에 데이터 저장, receiver는 receive buffer에 저장
- application이 준비되면 buffer에 있는 것들 읽음
- 핵심은 receive buffer가 안넘치는 것
- 따라서 receiver는 RWND: receive buffer에 남은 공간 홍보
