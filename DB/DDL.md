# DDL (데이터 정의어)

##### ※ Data Definition Language

- 테이블, 시퀀스, 뷰 인덱스 등의 DB에서 사용하는 오브젝트 구조를 정의하는 퀴리문
  - **CREATE** 		 : DB 오브젝트 생성
  - **DROP**              : DB 오브젝트를 삭제
  - **TRUNCATE**     :  오브젝트 완전 삭제
  - **ALTER**             : 오브젝트 수정



### #CREATE문

- CREATE TABLE 테이블명 (컬럼이름1 컬럼 타입1, 컬럼이름2 컬럼타입2 ....);

  ```sql
  CREATE TABLE coffee(
  	id NUMBER(2),
      name VARCHAR2(50),
      price NUMBER(4)
  );
  ```


