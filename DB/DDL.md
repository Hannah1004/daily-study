# DDL (데이터 정의어)

##### ※ Data Definition Language

- 테이블, 시퀀스, 뷰 인덱스 등의 DB에서 사용하는 오브젝트 구조를 정의하는 퀴리문
  - **CREATE** 		 : DB 오브젝트 생성
  - **DROP**              : DB 오브젝트를 삭제
  - **TRUNCATE**     :  오브젝트 완전 삭제
  - **ALTER**             : 오브젝트 수정

#### # 컬럼 타입

- **NUMBER(n), NUMBER(n,m)**

  - 숫자 데이터만 저장할 수 있는 컬럼 타입

  - 숫자가 하나만 적혀있으면 정수를 저장할 수 있고,

    두개 적혀있으면 소수점까지 저장할 수 있다.

  - NUMBER(n) : n자리 정수를 저장할 수 있는 컬럼

  - NUMBER(n,m) : (n-m)자리 정수와 m자리 소수를 저장할 수 있는 컬럼

- **VARCHAR2(n)**

  - 가변 길이 문자 데이터를 저장하는 컬럼 타입

  - 저장되는 데이터의 크기에 맞춰서 알맞은 공간만 사용하는 타입

  - VARCHAR(10) 크기로 설정된 컬럼에 2글자만 들어온다면

    2글자 만큼의 공간만 차지한다.

  - 가변적인 데이터를 저장할 때는 용량을 많이 절약할 수 있다.

- **CHAR(n)**

  - 고정 길이 문자 데이터를 저장하는 컬럼 타입

  - 설정된 길이보다 적은 양의 데이터가 들어오더라도

    설정된만큼의 공간을 모두 차지한다.

  - CHAR(10)크기로 설정된 컬럼에 2글자만 들어온다면 

    10글자 만큼의 공간을 모두 차지한다.

  - 데이터가 낭비될 수는 있지만 크기 계산을 아예 하지 않는다는 장점이 있다.

- **DATE**

  - 날짜 및 시간을 저장하는 컬럼 타입

### #CREATE문

- CREATE TABLE 테이블명 (컬럼이름1 컬럼 타입1, 컬럼이름2 컬럼타입2 ....);

  ```sql
  CREATE TABLE fruit(
  	fid NUMBER(2) PRIMARY KEY,
      fname VARCHAR2(50) NOT NULL,
      fprice NUMBER(4) DEFAULT 1000 NOT NULL 
      				-- NULL일때는 1000으로 기본값 해줌
  );
  ```

### # DROP문

- DROP TABLE 테이블명;

##### # 삭제된 테이블, 인덱스들이 담겨있는 휴지통

- SHOW RECYCLEBIN;
- SELECT * FROM recyclebin;

##### # 휴지통에서 복구하기

- FLASHBACK TABLE 테이블명 TO BEFORE DROP;

##### #휴지통 비우기(완전히 삭제)

- PURGE RECYCLEBIN;

### #ALTER문

- 이미 존재하는 테이블에 컬럼 **추가하기**

  - **ALTER TABLE 테이블명 ADD (컬럼명 컬럼타입(길이) 제약조건);**
  - 이미 행이 존재하는 테이블에 새로운 컬럼을 추가하기 위해서는 기본값이 필요

  ```sql
  ALTER TABLE fruit ADD (origin_code CHAR(2));
  -- FFFFFF는 흰색을 의미
  ALTER TABLE fruit ADD (color CHAR(6) DEFAULT 'FFFFFF' NOT NULL);
  ```

- 이미 존재하는 컬럼을 **수정하기**

  - **ALTER TABLE 테이블명 MODIFY (컬럼명 컬럼타입(길이) 제약조건);**
  - 제약조건을 적지 않으면 해당 컬럼의 제약조건이 그대로 유지된다.
  - 제약조건을 바꾸고 싶다면 바꾸고 싶은 제약조건을 적을 수 있다.

  ```sql
  ALTER TABLE fruit MODIFY (color CHAR(6) DEFAULT '000000');
  ALTER TABLE fruit MODIFY (fid NUMBER(5));
  ```

