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
### 1. 흐름제어
- 수신측이 송신측보다 빠르면 상관 없지만 반대의 경우 문제가 생김
- 수신측의 용량을 초과한 이후 오는 데이터들은 손실의 우려, 손실된다면 불필요한 응답과 수신이 데이터간 빈번히 발생
- 그래서 송신 측의 데이터량을 수신측에 따라 조절
- ** 해결방법 **
> - Stop and Wait: 매번 전송한 패킷에 대해 응답을 보내야 다음 패킷 전송
> - Sliding Window
>> - 수신측에서 설정한 윈도우의 크기만큼 송신측에서 확인응답 없이 세그먼트를 전송할 수 있게 하여 데이터 흐름 동적으로 조절
>> - 목적: 전송은 되었지만 acked를 받지 못한 byte의 숫자를 파악하기 위한 프로토콜
>> - 동작방식: 윈도우에 포함되는 모든 패킷을 저장하고, 그 패킷들의 전달이 확인되는대로 이 윈도우를 옆으로 옮겨 다음 패킷 전송
>> - Window: TCP/IP를 사용하는 모든 호스트들은 송신하기 위한 것과 수신하기 위한 2개의 window를 가지고 3 way handshaking으로 send window 사이즈 맞춤
> - 세부구조
>> 1. 송신버퍼
>> - 200 이전은 전송 및 확인 응답을 받았고 200 ~ 202는 확인응답 X 203 ~ 211 은 전송 X
>> 2. 수신 윈도우
>> 3. 송신 윈도우
>> 4. 송신 윈도우 이동
>> 5. Selected Repeat