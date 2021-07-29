# JOIN

### ※ 알아 둬야할 개념

#### # 기본키

- Primary Key(PK)

- 한 테이블에서 하나의 행을 유일하게 구분할 수 있는 컬럼

- 한 테일블 당 하나 밖에 설정할 수 없다.

- 기본키가 될 수 있는 컬럼이지만 기본키로 설정되지 않은 컬럼은 

  '후보키(Candidate Key)' 라고 한다.

- 기본키로 설정된 컬럼에는 중복된 값을 넣을 수 없고(UNIQUE),

  비어있는 값도 허용하지 않는다.(NOT NULL)

#### # 외래키

- Foreign Key(FK)

- 다른 테이블에서는 기본키 또는 후보키(또는 중복값이 없는 컬럼)이지만

  해당 테이블에서는 중복되는 값인 컬럼

  ex : employees의 department_id는 employees에서는 중복을 허용하는 컬럼이지만

  	departments 테이블에서는 기본키로 사용되는 컬럼이다.

- 외래키가 설정된 테이블끼리는 관계가 형성된 것으로 볼 수 있다.

- 외래키로 지정된 컬럼에는 반드시 참조하는 컬럼에 이미 존재하는 값만 추가할 수 있다.

### 관계

#####  # 1 : n 관계

- 하나의 부서에 여러명의 사원이 소속될 수 있다.
- 한명의 담임 선생이 여러명의 학생을 맡는다.
- 하나의 제품에 여러개의 부품이 조립된다.

##### # n : n 관계

- 하나의 제품에 여러개의 부품이 조립된다.

  하지만 부품은 다른 제품에도 사용될 수 있다.


## #테이블 JOIN

- 기본키와 외래키를 통해 관계가 형성되어 있는 각 테이블들의 정보를 종합하여 조회하는 것



### # CROSS JOIN

- 조인에 사용되는 테이블들의 모든 행을 조합하여 나올 수 있는 모든 경우를 출력하는 JOIN
- 그냥 모든 경우를 출력하는 쓸모없는 JOIN

### # EQUI JOIN

- 두 테이블 간의 서로 동일한 값을 지닌 컬럼을 이용하여

  CROSS JOIN에서 의미있는 결과만 남기는 JOIN

  ```sql
  -- 연습1 : first_name이 H로 시작하는 사원들의 사원번호/이름/부서이름을 조회
  SELECT employee_id, first_name, department_name
  FROM employees e, departments d
  WHERE first_name LIKE 'H%'
  	  AND e.department_id = d.department_id;
  ```

### # SELF JOIN

- 하나의 테이블 내에서 자기 자신과 JOIN하여 원하는 데이터를 얻어내는 조인 방식

- 외래키가 자기 테이블의 기본키 컬럼을 참조하는 경우

  ex : employees의 manager_id는 직장 상사의 사원번호를 저장하는 외래키이다.

  ```sql
  SELECT
      a.first_name AS 사원이름,
      b.first_name AS 직장상사
  FROM
      employees  a,
      employees  b
  WHERE
      a.manager_id = b.employee_id
  ORDER BY
      a.employee_id;
  ```

### # OUTER JOIN

- JOIN 조건을 만족하지 못해서 등장하지 못했던 행들을 확인 할 수 있는 JOIN

- (+)를 붙인 쪽의 컬럼에 null을 추가해서 반대쪽에서 등장하지 못한 행들을 확인한다.

  ```sql
  -- 연습1 : 사원번호/이름/부서이름/도시를 출력하되 소속된 사원이 없는 도시도 출력해보세요
  SELECT
      employee_id AS 사원번호,
      first_name AS 이름,
      department_name AS 부서이름,
      city AS 도시
  FROM
      employees    e,
      locations    l,
      departments  d
  WHERE
      l.location_id = d.location_id(+)
      AND e.department_id(+) = d.department_id
  ORDER BY employee_id desc, department_name desc;
  ```
