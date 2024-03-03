# CPU 스케쥴링
### 1. 스케쥴링
CPU를 사용하기 위해 프로세스 잘 배정하기
- 조건: 오버헤드↓, 사용률↑, 기아현상↓
- 목표
> 1. Batch System: 시간보다 처리량 중요
> 2. Interactive System: 빠른 응답, 적은 대기
> 3. Real time System: 기한 맞추기
### 2. 선점/ 비선점 스케쥴링
- 선점: OS가 CPU의 사용권을 선접할 수 있는 경우, 강제 회수하는 경우
> Interrupt, I/O or Event Completion, I/O or Event Wait, Exit
- 비선점: 프로세스 종료 or I/O등의 이벤트가 있을 때까지 실행 보장
> I/O or Event Wait, Exit
### 3. Process 상태
##### 프로세스의 상태 전이
- 승인: 프로세스 생성이 가능하여 승인
- 스케쥴러 디스패치: 준비상태중에 있는 프로세스 중 하나를 선택하여 실행
- 인터럽트: 입출력, 예외, 이벤트 등이 발생하여 현재 실행중인 프로세스르르 준비상태로 바꿈
- 입출력 또는 대기: 실행중인 프로세스를 입출력, 이벤트가 끝날 때까지 대기
- 입출력 또는 이벤트 완료: 입출력/이벤트가 끝난 프로세스를 준비 상태로 전환하여 스케줄러에 의해 선택될 수 있도록
### 3. CPU 스케쥴링 종류
- 비선점 스케쥴링
> 1. FCFS(First come First Served)
> - 큐에 도착한 순서대로 CPU 할당
> - 실행시간이 짧은게 뒤로 가면 평균 대기시간 길어짐
> 2. SJF( SHort Job First)
> - 수행시간이 짧다고 판단되는 것 먼저
> - FCFS보다 평균 대기시간 감소
> 3. HRN(Hit Rresponse-ratio Next)
> - 우선순위 계산하여 점유 불평등 보완
> - 우선순위 = (대기시간 + 실행시간) / 실행시간
- 선점 스케쥴링
> 1. Priority Scheduling
> - 정적/동적으로 우선순위를 부여하여 우선순위가 높은 것 부터 처리
> - 우선순위가 낮은 프로세스가 무한정으로 기다리는 Starvation이 생길 수 있음
> - Aging방법으로 Starvation 해결 가능
> 2. Round Robin
> - FCFS에 의해 프로세스들이 보내지면 각 프로세스는 동일한 시간의 Quantum 만큼 CPU 할당 받음
>> TimeQuantum: 실행의 최소단위 시간
> - TimeQuantum이 크면 FCFS와 같고 작으면 Context Switching이 잦아 오버헤드 자주 발생
> 3. Multilevel Queue
> - 작업들을 여러종류의 큐로 나누어 여러개의 큐를 이용하는 기법
> - 우선순위 낮은 큐들이 실행하지 못하는 것을 방지하고자 각 큐마다 다른 Time Quantom 설정
> - 우선순위가 높은 큐는 작은 Time Quantum, 우선순위가 낮은 큐는 높은 Time Quantom
> 4. Multilevel Feedback Queue
> - 다단계 큐에서 자신의 Time Quantum 다 채운 큐는 밑으로 내려가고 아닌 큐는 유지
>> Time Quantum을 다 채운 프로세스는 CPU Burst로 판단하기 때문
> - 짧은 작업에 유리, 입출력 많은 작업에 우선순위(Interrupt 많기 때문)
### 4. CPU 스케쥴링 척도
1. Respose Time
> 작업이 처음 실행까지 걸린 시간
2. Turnaround Time
> 실행 시간과 대기 시간을 모두 합한 시간으로 작업이 완료될 때 까지 걸린 시간