# SQL(Structured Query Language)

### 개요

**관계형 데이터베이스(RDBMS)** 에서 데이터를 조작, 처리하기 위한 표준 프로그래밍 언어이다.<br>

데이터베이스에 명령을 전달하는 역할을 한다.<br>

### SQL문(SQL Statement)의 분류

#### 1. 데이터 조작어, DML (Data Manipultaion Language)

`SELECT, INSERT, UPDATE, DELETE, MERGE`

테이블의 데이터(Row)를 조작한다.

#### 2. 데이터 정의어, DDL (Data Definition Language)

`CREATE, ALTER, DROP, RENAME, TRUNCATE, COMMENT`

Table, Index, View 등 데이터베이스 객체(Object)를 생성, 변경, 삭제한다.

#### 3. 데이터 제어어, DCL (Data Control Language)

`GRANT, REVOKE`

User의 권한을 제어한다.

#### 4. 트랜잭션 제어어, TCL (Transaction Control Language)

`COMMIT, ROLLBACK, SAVEPOINT`

IUD(Insert, Update, Delete) 등의 데이터 변경 작업을 **논리적인 단위인 트랜잭션**으로 묶고, 작업을 확정하거나 되돌린다.

### SELECT문의 구조

| **문법**       | **사용법**                                                     |
| -------------- | -------------------------------------------------------------- |
| **SELECT**     | `col1, col2 ..`, `func(col)`, `exp(표현식, 수식)`, `subquery`  |
| **FROM**       | `table1, table2 ..`, `table1 JOIN table2`, `subquery`          |
| **[WHERE]**    | `컬럼에 대한 조건절, 연산자 -> data 필터링`                    |
| **[GROUP BY]** | `그룹화 기준 컬럼명 지정`                                      |
| **[HAVING]**   | `그룹함수 컬럼(SUM, AVG, MIN ..)에 대한 조건절 -> data 필터링` |
| **[ORDER BY]** | `정렬 기준 컬럼 {ASC \| DESC} -> 기본값 ASC`                   |

### SELECT문의 실행 순서

FROM > WHERE > GROUP BY > HAVING > SELECT > ORDER BY

### 함수

> MYSQL 문법을 기준으로 작성하였습니다.

#### 대소문자 변환 함수

| **함수**  | **설명**      | **예제**               |
| --------- | ------------- | ---------------------- |
| **LOWER** | 소문자로 변환 | `LOWER('Test') = test` |
| **UPPER** | 대문자로 변환 | `UPPER('Test') = TEST` |

#### 문자 조작 함수

| **함수**       | **설명**                          | **예제**                                           |
| -------------- | --------------------------------- | -------------------------------------------------- |
| **CONCAT**     | 문자열 연결                       | `CONCAT('Study', 'Hard') = StudyHard`              |
| **SUBSTR**     | 문자열 일부 추출(시작 위치, 길이) | `SUBSTRING('StudyHard', 1, 5) = Study`             |
| **LENGTH**     | 문자열 길이 반환                  | `LENGTH('StudyHard') = 9`                          |
| **INSTR**      | 특정 문자 인덱스 반환             | `INSTR('StudyHard', 'H') = 6`                      |
| **LPAD, RPAD** | 좌/우를 특정 문자로 채움          | `LPAD(score, 5, '*')= **100`                       |
| **REPLACE**    | 특정 문자열 치환                  | `REPLACE('StudyHard', 'Hard', 'Easy') = StudyEasy` |
| **TRIM**       | 양 측 공백(혹은 특정 문자) 제거   | `TRIM(' StudyHard ') = StudyHard`                  |

#### 조건부 표현식 함수 CASE

```
SELECT cat_name,
  CASE cat_type
    WHEN 1 THEN '고등어'
    WHEN 2 THEN '치즈'
    WHEN 3 THEN '턱시도'
    ELSE '카오스'
  END
FROM cats;
```

#### 집계 함수

| **함수**  | **설명**       | **예제**           |
| --------- | -------------- | ------------------ |
| **COUNT** | 행의 개수 반환 | `COUNT(*) = 5`     |
| **SUM**   | 숫자 합계 반환 | `SUM(score) = 380` |
| **AVG**   | 평균값 반환    | `AVG(score) = 76`  |
| **MIN**   | 최소값 반환    | `MIN(score) = 60`  |
| **MAX**   | 최대값 반환    | `MAX(score) = 100` |
