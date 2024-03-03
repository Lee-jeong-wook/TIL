# PCB
Process Management
CPU가 여러개 있을 때 CPU 스케쥴링을 사용하여 ㄱ헌리하는 것
이떄 CPU는 각 프로세스들이 누군지 알아야 관리하는데
이 데이터를 ** Process Metadata **
### Process Metadata
- Process ID
- Process State
- Process Priority
- CPU Register
- Owner
- CPU Usage
- Memory Usage
메타데이터들은 생성되면 PCB(Process Control Block)으로 감
### PCB
1. 프로그램 실행
2. 프로세스 생성
3. 프로세스 주소 공산에 코드, 데이터, 스택 생성
4. 프로세스의 메타 데이터들이 PCB에 저장
##### For?
CPU에서는 프로세스의 상태에 따라 교체 작업이 이루어짐
이 떄 ** 앞으로 수행할 대기중인 프로세스에 관한 저장 값을 PCB에 저장 **
##### How to manage
Linked List 방식
PCB link head에 PCB들이 생성될 때마다 붙게됨
프로세스 생성 시 삽입, 완료 시 삭제