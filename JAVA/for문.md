# for문

- for(초기값; 반복조건; 증가폭){

  	가운데에 있는 반복조건이 true인 동안 반복될 명령어들을 적는 곳

  }

- 가장 기본적인 형태의 for문

  - 초기값에는 0을 주고 조건에는 반복하고 싶은 횟수를 적는다.
  - 증가는 1씩 한다.
  - 원하는 횟수만큼 반복하기 가장 좋은 형태의 for문

  ```java
  for(int i = 0; i <= 3; ++i){
   System.out.println("Hello World!" + i);
  }
  /*
  	Hello World!0	Hello World!1
  	Hello World!2	Hello World!3
  */
  ```

- 초기값, 증가값 조건은 마음대로 변경할 수 있다.

  ```java
  for(int i = 100; i > 0; --i){
      System.out.println(i);
  }
  // 100부터 1까지 출력됨
  ```
