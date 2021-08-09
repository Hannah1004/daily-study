# ANSI JOIN

- ANSI (American National Standars Insititute)

  미국에서 여러가지 IT 표준을 재정하는 단체

- 모든 RDBMS들은 ANSI 표준을 따르는 쿼리문을 가지고있다.

#### # ANSI CROSS JOIN

- 조인한 모든 행일 등장하는 JOIN

```sql
SELECT * FROM employees CROSS JOIN departments
```

#### # ANSI INNER JOIN

- 조인 조건에 맞는 행만 등장하는 JOIN

  ```sql
  SELECT * FROM employees e
      INNER JOIN departments d ON e.department_id = d.department_id;
  
  SELECT * FROM employees INNER JOIN departments USING(department_id);
  ```

#### # ANSI OUTER JOIN

- 조인 조건에 맞지 않는 행도 등장하는 JOIN

  ##### # LEFT OUTER JOIN

  - 왼쪽 테이블의 등장하지 못한 행이 등장한다.

  - (+)를 오른쪽에 붙인 것과 같다.

    ```sql
    SELECT * FROM employees
        LEFT OUTER JOIN departments USING (department_id);
    ```

  ##### # RIGHT OUTER JOIN

  - 오른쪽 테이블의 등장하지 못한 행이 등장한다.

  - (+)를 왼쪽에 붙인것과 같다.

    ```sql
    SELECT * FROM employees
        RIGHT OUTER JOIN departments USING (department_id);
    ```

  ##### # FULL OUTER JOIN

  - 각 테이블에서 등장하지 못했던 행들이 등장한다.

    ```sql
    SELECT * FROM employees
        FULL OUTER JOIN departments USING (department_id);
    ```



#### ※ ANSI JOIN을 사용하면 조인 조건과 행 조회 조건을 쉽게 구분할 수 있다.

```sql
SELECT * FROM employees 
    INNER JOIN departments USING(department_id)
    WHERE department_id BETWEEN 100 AND 200;
```



