# MySQL(DML, DDL)
## DML(데이터 조작어)
### 1. 데이터 조회
#### 문법 : SELECT [column명] FROM [table명];
#### 예시 : SELECT name FROM employee;

### 2. 데이터 삽입
#### 문법 : INSERT INTO [table명] SET [column1 명] = [저장값1], [column2 명] = [저장값2], ...;
#### 예시 : INSERT INTO employee SET name = '김모씨', departmentId = 1, salary = 5000;

### 3. 데이터 수정
#### 문법 : UPDATE [table명] SET [column1 명] = [수정값1], [column2 명] = [수정값2], ... WHERE [column명] = [조건값1] (AND | OR) ...;
#### 예시 : UPDATE employee SET name = '조모씨' WHERE id = 1;

### 4. 데이터 삭제
#### 문법 : DELETE FROM [table명] WHERE [column명] = [조건값1] (AND | OR) ...;
#### 예시 : DELETE FROM employee WHERE id = 1;

## DDL(데이터 정의어)
### 1. 테이블 생성
#### 문법 : CREATE TABLE [테이블명] ([column1 명] [column1 타입] [column1 제약조건], [column2 명] [column2 타입] [column2 제약조건]);
#### 예시 : CREATE TABLE employee (id int primary key, name varchar(100) not null);

### 2. 테이블 수정
#### 문법 : ALTER TABLE [테이블명] [변경할 내용];
#### 예시 : ALTER TABLE employee add column position varchar(100) not null;

### 3. 테이블 삭제
#### 문법 : DROP TABLE [테이블명];
#### 예시 : DROP TABLE employee;

---
# MySQL(Join, SubQuery)

## Join

**예시 Table A: EMPLOYEE (직원)**

| EMP_ID | NAME | DEPT_ID |
|---|---|---|
| 1 | Kim | 10 |
| 2 | Lee | 20 |
| 3 | Park | NULL |

**예시 Table B: DEPARTMENT (부서)**

| DEPT_ID | DEPT_NAME |
|---|---|
| 10 | Development |
| 20 | HR |
| 30 | Sales |

### 1. Inner Join
#### 문법 : SELECT [column1 명],[column2 명],[column3 명],... FROM [table1 명] INNER JOIN [table2 명] ON [table1의 연결고리 컬럼명] = [table2의 연결고리 컬럼명];
#### 예시 : SELECT E.NAME, D.DEPT_NAME FROM EMPLOYEE E INNER JOIN DEPARTMENT D ON E.DEPT_ID = D.DEPT_ID;

| NAME | DEPT_NAME |
|---|---|
| Kim | Development |
| Lee | HR |

### 2. Left Join
#### 문법 : SELECT [column1 명],[column2 명],[column3 명],... FROM [table1 명] LEFT JOIN [table2 명] ON [table1의 연결고리 컬럼명] = [table2의 연결고리 컬럼명];
#### 예시 : SELECT E.NAME, D.DEPT_NAME FROM EMPLOYEE E LEFT JOIN DEPARTMENT D ON E.DEPT_ID = D.DEPT_ID;

| NAME | DEPT_NAME |
|---|---|
| Kim | Development |
| Lee | HR |
| Park | **NULL** |

### 3. Right Join
#### 문법 : SELECT [column1 명],[column2 명],[column3 명],... FROM [table1 명] RIGHT JOIN [table2 명] ON [table1의 연결고리 컬럼명] = [table2의 연결고리 컬럼명];
#### 예시 : SELECT E.NAME, D.DEPT_NAME FROM EMPLOYEE E RIGHT JOIN DEPARTMENT D ON E.DEPT_ID = D.DEPT_ID;

| NAME | DEPT_NAME |
|---|---|
| Kim | Development |
| Lee | HR |
| **NULL** | Sales |

## SubQuery
### 1. SubQuery