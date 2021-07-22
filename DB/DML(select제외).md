# DML (데이터 조작어) -select 제외

##### ※ Data Manipulation Language

- **SELECT** : 데이터 조회
- **INSERT** : 데이터 생성(추가)
- **DELETE** : 데이터 삭제
- **UPDATE** : 데이터 수정

### #INSERT문

- INSERT INTO 테이블명 (컬럼명 ,...) VALUES (값, ...);

- 컬럼 순서를 원하는 순서대로 지정하여 추가할 수 있다.

- 넣고 싶은 컬럼에만 데이터를 추가할 수 있다.

- 컬럼명을 생략하면 순서대로 모든 컬럼에 데이터를 넣어야한다.

  ```sql
  INSERT INTO fruit (fid, fname, fprice) VALUES (1, '사과', 1500);
  INSERT INTO fruit VALUES (2, '오렌지', 2500);
  INSERT INTO fruit (fid, fname) VALUES (3, '파인애플');
  ```

- INSERT INTO 테이블명 (서브쿼리) : SELECT로 조회한 내용을 그대로 INSERT 할 수 있음.

  ​	ex : INSERT INTO fruit (SELECT * FROM fruit);

### # DELETE문

- DELETE FROM 테이블명 WHERE 조건절;

- **※ 조건을 지정하지 않으면 모든 행이 삭제된다.**

- 조건에 맞는 행을 모두 삭제한다.

- 하나의 행만 지우고 싶을 때는 주로 기본키와 함께 활용된다.

  ```sql
  DELETE FROM fruit;
  DELETE FROM fruit WHERE fname IS NULL;
  DELETE FROM fruit WHERE fid = 1;
  ```

### # UPDATE문

- UPDATE 테이블명 SET 컬럼=값 WHERE 조건;

- **※ UPDATE 조건을 설정하지 않으면 모든 행을 수정한다.**

- 조건을 만족하는 모든 행을 수정한다.

- 한번에 여러 컬럼의 값을 수정할 때는 ,를 이용한다.

- 하나의 행만 수정하고자 할 때는 기본키와 함께 사용한다.

  ```sql
  -- 모든 fname이 apple로 수정됨
  UPDATE fruit SET fname = 'apple';
  UPDATE fruit SET fid = 3, fname = 'orange', fprice = 1000;
  
  ```
