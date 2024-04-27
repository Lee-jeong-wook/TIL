# OS
### 대표적 운영체제
* Window: Microsoft사 유료 라이선스, 중소규모 및 개인용
* UNIX: IBM, HP, SUN제품, 유료로 대용량 처리
* Linux: Linux Torvalds사 제품으로 무료, 중대규모 서버
* IOS: 애플 제품으로 하드웨어 번들, 스마트폰, 태블릿

### 운영체제(OS)
목표
> 사용자가 사용하는 응용프로그램을 효율적으로, 적절하게 동작하도록 지원, 분배

위치
* 저장매체(SSD, HDD)에 저장

시스템자원
> * CPU, MEMORY
> * IO device
> * 저장매체(SSD, HDD)

역할
* **사용자와 컴퓨터를 이어주는 역할**
* CPU: 각 프로그램이 어느정도 사용할지 결정
* Memory: 어디에 어느정도 저장될지 결정
* 저장매체: 어떻게, 어디에 저장할지 결정
* 키보드/마우스: 스스로 표시 불가

자세히
* Shell - UI: GUI, Batch, CommandLine
* System Call
* 프로세스 관리
* 주기억장치 관리
* 파일 관리
* 디스크 관리
* 입출력 관리
* 네트워크 보안

응용프로그램
OS는...
* 응용프로그램을 실행시키고
* 권한을 관리하고
* 응용프로그램 사용하는 사용자 관리

응용프로그램은...
* 누구나 만들 수 있음(오류는 책임지지 않음)
* 그래서 운영체제가 관리

역사
1. 1950(ENIAC)
> * 운영체제 없음
> * 1개 응용프로그램 실행도 바빴ㄷ음
> * 응용프로그램이 시스템자원 제어
2. 1960 초
> * 프로그램 많아지고 유저 많아짐
> * 배치 처리 시스템 등장

※배치 처리 시스템이란
* 여러 응용프로그램을 등록해 놓으면 순차적으로 실행하는 시스템
* 단점은 앞에 실행시간이 긴 프로그램이 있으면 오래 걸림

3. 1960 후
* 시분할과 멀티태스킹의 **개념** 등장
※시분할 시스템이란
* 다중 사용자를 지원하고, 컴퓨터 응답시간을
최소화하는 시스템

※멀티 태스킹이란
* 단일 CPU에서 여러 응용 프로그램의 병렬 실행을
가능하게 하는 시스템

4. 1970
* 제대로 된 운영체제 등장(UNIX)
* 이 전에는 어셈블리로 귀찮게 여러번
* 지금부턴 C로 한번
* 멀티 태스킹, 시분할 시스템, 멀티 프로그래밍 모두 사용
* 대형 컴퓨터를 여러명이 사용
5. 1980
* 개인용 컴퓨터 시대
* CLI, GUI
6. 1990
* 응용프로그램 by GUI
* Window 대중화
* 엑셀 등등 등장
7. 1990
* 네트워크 발전으로 오픈소스
* 오픈소스 활성화(리눅스, 앞파치 mysql)
* 가상머신, 대용량 병령 처리 활성화