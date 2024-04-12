# Process
### 프로세스 구조
* Text
* Data : 변수, 초기화된 데이터
* Stack : 임시 데이터(함수호출, 로컬 변수)
* Heap : 코드에서 동적으로 만들어지는 데이터
* **PC(Program couter) + SP(Stack Pointer)**
### PCB(Process control block,Process context block )
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