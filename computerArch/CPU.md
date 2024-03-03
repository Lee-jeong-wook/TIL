# CPU
### What?
CPU는 인간의 두뇌 역할
크게 레지스터, 연산장치, 제어장치로 구분
##### 연산장치
- 산술과 논리 연산 실행,
- 연산에 필요한 값을 레지스터에서 가져오고 연산결과를 레지스터로 보냄
##### 제어장치
- 명령어를 순서대로 실행하도록 제어
- 주기억장치에서 명령어 해독, 그 명령어에 따른 제어신호를 기억장치, 연산장치, 입출력 장치로 보냄
##### 레지스터
- 고속기억장치로 명령어 주소, 코드, 데이터, 연산 결과 임시 저장
- 용도에따라 범용과 특수로 나뉨
- 중앙처리장치 종류에 따라 사용할 수 있는 레지스터 개수와 크기가 다름
> - 범용레지스터는 연산에 필요한 데이터나 결과를 임시 저장
> - 특수레지스터는 다른 특수한 용도로 사용
##### 특수목적 레지스터
- MAR(메모리 주소 레지스터): 읽기와 쓰기 연산을 수행 할 주기억장치 주소 저장
- PC(프로그램 카운터): 다음에 수행할 명령어 주소 저장
- IR(명령어 레지스터): 실행중인 명령어 저장
- MBR(메모리 버퍼 레지스터): 주 기억장치에서 읽어온 데이터나 저장할 데이터 임시 저장
- AC(누산기): 연산 결과 임시 저장   
### 동작과정
1. 주기억장치는 입력장치에서 입력받은 데이터 혹은 보조기억장치에서 저장된 프로그램 읽어옴
2. 프로그램을 실행하기 위하여 주기억장치에 저장된 프로그램 명령어와 데이터를 읽어와 처리하고 결과를 주기억장치에 저장
3. 주기억장치는 처리 결과를 보조기억장치에 저장하거나 출력장치로 보냄
4. 제어장치는 이 위 과정들을 제어
### 명령어 세트란?
CPU가 실행할 명령의 집합체
연산코드 + 피연산자
> 연산코드: 실행할 연산
> - 연산, 제어, 데이터 전달, 입출력 기능 가짐
> 피연산자: 저장될 위치, 필요 데이터
> - 주소, 논리 데이터 저장
CPU는 프로그램 해독을 위해 주기억장치에서 명령어를 순차적으로 인출하여 해독하고 실행하는 과정 반복
이 하나의 명령어를 인출하는데 필요한 과정을 명령어 사이클 이라고 함
명령어 사이클은 인출, 실행, 간접, 인터럽트
주기억장치에 기억된 주소로 명령어를 가져오고, 실행하고, 인출함
##### 명령어 처리 과정
> 가장 중요 부분은 PC값의 증가
인출과정
- PC에 저장된 주소를 MAR로 전달
- 저장된 내용을  토대로 주기억장치의 주소에서 명령어 인출
- 인출한 명령어 MBR에 저장
- 다음 명령어 인출 위에 PC값 증가
- MBR에 저장된 내용을 IR에 전달
실행과정
> ADD addr 명령어 연산
이미 인출이 되었기에 PC 증가 X
IR에는 MBR 값이 저장되었으니 AC에 MBR값 더함