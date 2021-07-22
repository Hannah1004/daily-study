# SELECT문

- **※ SELECT 컬럼명 FROM 테이블명;**

  - 데이터를 조회하는 쿼리문
  - 컬럼명에 *를 쓰는 것은 모든 컬럼을 뜻한다.
  - 쿼리문은 대소문자를 구분하지 않는다.
  - 컬럼명/ 테이블명은 대소문자를 구분하지 않는다.
  - 테이블에 저장되는 데이터는 대소문자를 구분한다.

  ```sql
  -- 이 계정에 있는 모든 테이블을 보여줌
  SELECT * FROM tabs;
  
  SELECT * FROM employees;
  SELECT * FROM jobs;
  
  SELECT employee_id, email FROM employees;
  ```

- **AS**(별칭)

  - 컬럼명 AS 별칭
  - AS에 스페이스바를 넣어주려면 ""안에 넣어야한다.

  ```sql
  SELECT
  	employee_id AS 사원번호,
  	last_name AS 성,
  	salary * 0.8 AS "깍인 월급"
  FROM employees;
  ```

- 쿼리문에 **산술연산자** 이용 가능

  ```sql
  SELECT last_name, salary FROM employees;
  SELECT last_name, salary + 500 FROM employees;
  SELECT last_name, salary * 12 FROM employees;
  ```

- **NVL**(컬럼명, 대체값)

  - 해당 컬럼에서 NULL값이 나왔을 때  NULL 대신 사용할 값을 설정한다.

    (NULL값을 연산하게 되면 무조건 NULL이 나온다.)

  ```sql
  SELECT
  	last_name, 
  	salary AS 급여,
  	salary * (1 + NVL(commission_pct, 0)) AS "커미션 적용"
  FROM
  	employees;
  ```

- **DISTINCT** : 하나의 값이 단 한번만 출력된다.(중복된 값은 한번만 출력됨)

  ```sql
  SELECT DISTINCT job_ic FROM employees;
  ```



##  WHERE절

**※ SELECT문에 조건을 추가하여 해당 조건을 만족하는 행들만 조회할 수 있다.**

#### ※SELECT 컬럼명 FROM 테이블명 WHERE 조건절

- **비교 연산자**

  	= : 같다.

  	<, >, <=, >= : 비교

  	!=, <>, ^= : 다르다

  ```sql
  SELECT * FROM employees WHERE salary = 7000;
  SELECT * FROM employees WHERE salary > 7000;
  SELECT * FROM employees WHERE salary <= 7000;
  SELECT * FROM employees WHERE salary <> 7000;
  
  -- 데이터는 대소문자를 구분한다.
  SELECT * FROM employees WHERE first_name > 'Oliver';
  ```

- **AND, OR, NOT**

  ```sql
  SELECT * FROM employees WHERE hire_date < '03/06/17'
  						AND hire_date > '02/01/01';
  ```

- **IN**(A, B, ...)

  - ()안의 내용 중 하나인 경우 참

  ```sql
  -- 사원테이블에서 부서id가 30 또는 60인 사원의 이름 조회
  SELECT first_name FROM employees WHERE department_id IN(30, 60);
  ```

- **NULL값**은 값이 아니기에 어떤 값과도 크기 비교가 불가능하다.

  ```sql
  SELECT * FROM employees WHERE email != NULL;
  SELECT * FROM employees WHERE email IS NULL;
  SELECT * FROM employees WHERE email IS NOT NULL;
  ```

- **NOT의 위치는 자유롭다.**

  ```sql
  SELECT * FROM employees WHERE department_id NOT IN (30,60,90);
  SELECT * FROM employees WHERE NOT department_id IN (30,60,90);
  ```



#### # LIKE 문법

- 데이터의 일부분으로 원하는 내용을 검색할 수 있는 문법

- 문자타입과 날짜타입에 모두 사용 가능

- % : 길이 제한 없이 아무 문자열이나 와도 되는 자리 (없는 것도 됨)

- _ : 하나의 아무 문자나 와도 되는 자리

  ```sql
  -- 이름이 a로 끝나는 모든 사원을 조회
  SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '%a';
  
  -- 이름에 e가 두개 이상 포함된 모든 사원을 조회 
  SELECT * FROM employees WHERE first_name LIKE '%e%e%';
  
  -- 이름이 다섯 글자면서 가운데에 a또는 e가 들어가는 모든 사원을 조회
  SELECT * FROM employees WHERE first_name LIKE '_____' 
  			AND (first_name LIKE ' _%a%_' OR first_name LIKE '_%e%_');
  ```



#### # UNION ALL (합집합)

```sql
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__a__'
UNION ALL
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__e__';
```

#### # INTERSECT (교집합)

```sql
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__a__'
UNION ALL
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__e__'
INTERSECT
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__a__';
```



#### # MINUS (차집합)

```sql
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__a__'
MINUS
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '__e__';
```

