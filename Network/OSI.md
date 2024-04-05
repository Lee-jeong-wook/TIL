# OSI 7계층
1. 물리(Pfysical)
> 리피터, 허브
- 데이터 전송 역할
2. 데이터 링크
> 브릿지, 스위치
- 물리계층으로 송수신된 정보를 안전하게 관리 및 전달
3. 네트워크
> 라우터, IP
- 데이터를 목적지까지 빠르고 안전라게
- 라우터를 이용해 이동할 경로를 선택하여 IP 주소 지정, 경로에 따라 패킷 생성
> 패킷은 네트워크를 통해 전달되는 형식화된 데이터 덩어리
- 라우팅, 흐름제어, 오류제어, 세그먼테이션 등 수행
4. 전송
> TCP UDP
- TCP UDP 통해 통신 활성화 이후 포트를 열고 프로그램들이 전송하도록 도움
> TCP: 신뢰성, 연결지향적
> UDP: 비신뢰성, 비연결성, 실시간
5. 세션
> API, Socket
- 데이터가 통신하기 위한 논리적 연결 담당, TCP/IP 섹션을 만들고 없애는 담당
6. 표현
> JPEG, MPEG 등
- 데이터표현에 독립성 제공 암호화 역할
- 파일 인코딩, 명령어 포장, 압축, 암호화
7. 응용
> HTTP, FTP, DNS 등
- 최종목적지, 응용 프로세스와 직접 관계하여 일반적인 응용 서비스 수행
- 사용자 인터페이스, 잔자 우편, DB 관리