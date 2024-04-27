# Process
### 프로세스란
* CPU를 수행되는 사용자 및 시스템 프로그램
* 시스템의 작업단위
* 운영체제 내의 PCB를 가진 프로그램
* 병행 수행 가능
* 수시로 프로세스들 사이를 다중화하여 전환
### 프로세스 상태
* 생성
> 프로세스의 최초 상태로 보조기억장치에 저장
* 준비
> 프로세스가 CPU를 사용하여 실행 준비, 준비 리스트에 들어가 우선순위에 의해 정렬됨
* 실행
> 프로세스가 CPU를 차지하여 실행, 명령어들 실행중인 상태
* 대기
> 기다림 또는 블록, IO동작 완료나 사건 발생 기다림, 블록 리스트에 있음
* 종료
> 실행 완료되어 자원 반납
### 프로세스 상태 전이
* Dispatch
> 준비 -> 실행 <br>
> 생성 상태에서 프로세스만 할당 받으면 실행 상태, 준비 프로세스 중 하나가 CPU에 할당받아 전이 스케쥴링 알고리즘에 의해 수행
* Timeout
> 실행 -> 준비 <br>
> 일정 시간 지나면 스케쥴러에 의해 PCB에 저장, 반납 이후 준비
* Block
> 실행 -> 대기 <br>
> IO 등 자원 요청 이후 전이, IO 자원은 CPU아닌 IO 프로세스 담당
* Wake up
> 대기 -> 준비 <br>
> 필요한 자원 할당되면 준비,
* Swap-out
> 준비 -> 지연, 대기 -> 지연 <br>
> 프로세스 생성 이후 메모리 부족, 준비 상태 이후 기억장치를 잃으면 커널이 메모리 회수
* Swap-in
> 지연 -> 준비, 지연 -> 대기 <br>
> 기억장치가 할당되면 디스크에서 다시 활동중인 메모리로 전이
### 프로세스 구조
* Text : 코드
* Data : 변수, 초기화된 데이터
* Stack : 임시 데이터(함수호출, 로컬 변수)
* Heap : 코드에서 동적으로 만들어지는 데이터
* **PC(Program couter) + SP(Stack Pointer)**
### PCB(Process control block,Process context block, 프로세스 제어 블록 )
* 운영체제 커널의 자료구조
* 운영체제가 프로세스 스케쥴링을 위해 프로세스에 관한 정보를 가진 DB
* PC와 SP 저장
* Process id
* Register 값   (PC, SP)
* Scheduling info(Process state)
* Memory Info(메모리 사이즈 limit)

### 프로세스와 컨텍스트 스위칭
* Context Switching(문맥 교환)
> CPU에 실행할 프로세스 교체 기술
1. 실행 중지할 정보를 해당 프로세스의 PCB에 업데이트하며 메인 메모리에 저장
2. 다음 실행할 프로세스 정보를 메인 메모리에 있는 PCB정보(PC, SP)를 CPU 레지스터에 넣고 실행
* 오래 걸리면 흔히 말하는 렉

### 컴파일러
* 초기 컴퓨터는 어셈블리어로 작성
* 컴파일러 등장(어셈블리어보다 느림, 재작성 X)
* 리눅스의 컨텍스트 스위칭 코드는 각CPU마다 별도 존재

### IPC
* 프로세스가 서로 공간을 쉽게 접근하면 위험
* 프로세스간 커뮤니케이션(IPC에서 커널 통함)
* 성능을 높이기 위해 여러 프로세스를 실행하며 상태 확인 및 데이터 송수신