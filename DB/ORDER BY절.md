# ORDER BY절

- 테이블을 조회할 때 원하는 컬럼 기준으로 정렬하여 조회할 수 있다.

- ORDER BY 컬럼명 [ASC|DESC]

  - ASC : ASCENDING(오름차순)
  - DESC : CESCENDING(내림차순)

- 오름차순/내림차순을 설정하지 않으면 기본적으로 오름차순으로 정렬한다.

  ```sql
  SELECT * FROM employees ORDER BY frist_name;
  SELECT * FROM employees ORDER BY frist_name ASC;
  SELECT * FROM employees ORDER BY frist_name DESC;
  ```

- 여러개의 정렬 기준을 적용할 수 있다.

```sql
-- 연습1 : 이름에 e가 두개 이상 포함된 사원들을 월급이 높은 순서대로 조회
SELECT * FROM employees WHERE lower(first_name) LIKE '%e%e%'
			ORDER BY salary DESC;

-- 연습2 : 30번, 60번, 90번 부서의 사원들을 부서번호 기준 오름차순으로 조회하고
--         같은 부서의 사원들은 가족 이름 알파벳순으로 정렬
SELECT * FROM employees WHERE department_id IN (30, 60, 90) 
			ORDER BY department_id, last_name;
```

