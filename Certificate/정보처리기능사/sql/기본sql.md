# 기본 sql
## DDL
### 개념
**데이터를 정의하는 언어**, 엄밀히는 데이터를 담는 그릇, DBMS에서 **'오브젝트'**
* 스키마
> * DBMS의 특성과 환경을 감안한 데이터 구조
> * 직관적인 하나의 DB로 이해
* 도메인
> * 속성의 데이터 값과 크기, 제약조건 등을 지정한 정보
> * 속성이 가질 수 있는 값의 범위로 이해 가능
* 테이블
> * 데이터 저장공간
* 뷰
> * 하나의 물리 테이블에서 유도되는 가상의 논리 테이블
* 인덱스
> * 검색을 빠르게 하기 위한 데이터 구조
### 유형
* 생성: CREATE
* 변경: ALTER
* 삭제: DROP(모두 삭제)
* 삭제: TRUNCATE(내용 삭제, 구조 유지)
* 변경: RENAME(이름 변경)
### 제약조건 적용
* PK
> * 기본키
> * NOT NULL, UNIQUE
* FK 
> * 외래키, 열 이름
> * 참조 무결성 위배 상황 발생 시 처리 방법으로
옵션 지정 가능
> * NO ACTION, SET DEFAULT, SET NULL, CASCADE, RESTRICT
* UNIQUE: 유일 값
* NOT NULL: 비면 안됨
* CHECK: 개발자 정의
## DML
### 개념
데이터 조작하는 명령어(데이터 관점에서 생명 주기에서 제어하는 것을 의미)
### 유형
* SELECT: 테이블 내용 조회
* DELETE: 테이블 내용 삭제(특정 컬럼만 삭제할 수 없음)
* UPDATE: 테이블 내용 변경
* INSERT: 테이블 내용 추가
### 사용 요소
##### OPTION
* ALL: 중복을 포함한 조회 결과 출력
* DISTINCT: 중복 제거
##### COLUMNS
* 컬럼명: SELECT로 선택
* 와일드카드: *
##### 기타 명령어
* BETWEEN : A AND B, 즉 A값과 B값 사이를 만족하는 부분을 검색한다.
* IN : IN(A, B), OR과 동일하게 참조하는 부분 중 하나라도 만족하는 부분을 검색한다.
* ORDER BY : 오름차순은 ASC, 내림차순은 DESC를 사용하여
정렬한다.
* HAVING : GROUP BY에 의해 그룹으로 분류된 부분에서
WHERE 대신 조건절을 대신한다.
## DCL
### 개념
데이터 이외의 오브젝트 제어가 필요
### 오브젝트 유형
* 사용자 권한
> * 접근 통제: 사용자 등록, 사용자에게 특정 DB 사용하도록 권한 부여
* 트랜잭션
> * 안전한 거래 보장: 동시에 다수 작업을 독립적으로 안전하게 처리하기 위해
### 유형
* DCL
> * GRANT: 사용자 권한 부여
> * REVOKE: 사용자 권한 회수
* TCL
> * COMMIT: 트랜잭션 확정
> * ROLLBACK: 트랜잭션 취소
> * CHECKPOINT: 복귀지점 설정
### 권한 종류
* 시스템 권한
> * CREATE USER: 계정 생성 권한
> * DROP USER: 계정 삭제 권한
> * DROP ANY TABLE: 테이블 삭제 권한
> * CREATE SESSION: DB 접속 권한
> * CREATE TABLE: 테이블 생성 권한
> * CREATE VIEW: QB TODTJD RNJSGKS
> * CREATE SEQUENCE: 시퀸스 생성 권한
> * CREATE PROCEDURE: 함수 생성 권한
* 객체 권한
> * ALTER: 테이블 변경 권한
> * INSERT: 데이터 조작 권한
> * DELETE
> * SELECT
> * UPDATE
> * EXECUTE ON PROCEDURE: 실행 권한