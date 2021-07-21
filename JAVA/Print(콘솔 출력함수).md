# Print(콘솔 출력함수)

#### print()

- 줄을 자동으로 바꿔주지 않음

  ```java
  System.out.print("Hello");
  System.out.print("Hello");
  
  // 결과 => HelloHello
  ```

#### println()

- 줄을 자동으로 바꿔줌

- ()에 전달한 데이터 맨뒤에 \n을 추가하여 출력

- ()에 아무것도 전달하지 않으면 \n만 출력

  ```java
  int apple = 17;
  System.out.print("사과 : ");
  System.out.println(apple + "개")
      
  // 결과 => 사과 : 17개
  ```

#### printf()

- 서식을 이용해 원하는 형태를 쉽게 만들어 출력하는 함수

- 출력의 형태를 미리 만들고 서식 문자 자리에 값을 순서대로 채워서 사용

- 문자열을 +로 이어붙이는 방식보다 편리한 경우에 사용

- 줄을 자동을 바꿔주지 않음(\n필요)

  ##### #서식문자 종류

  - %d : 해당 자리에 전달한 정수값을 10진수로 출력
  - %x : 해당 자리에 전달한 정수값을 16진수로 출력
  - %o : 해당 자리에 전달한 정수값을 8진수로 출력
  - %s : 문자열
  - %c : 문자
  - %f : 실수

  ```java
  int year = 2021, month = 5, day = 10, hour = 15, minute = 50;
  System.out.printf("%d년 %d월 %d일 \t %d:%d:%d\n", 
                     year, month, day, hour, minute, second);
  
  // 결과 => 2021년 5월 10일	15:50:30
  ```

  ##### #서식문자 옵션

  - %숫자d, %숫자s
    - 자릿수를 숫자만큼 확보하면서 오른쪽 정렬하여 출력
  - %-d
    - 자릿수를 숫자만큼 확보하면서 왼쪽정렬하여 출력

  - %0숫자d

    - 자릿수를 숫자만큼 확보하고 빈자리에 0을 채워 출력

  - %+d

    - 양수 앞에도 부호를 붙여서 출력

  - %.숫자f

    - 소수의 자릿수를 설정 (반올림도 해줌)

    ```java
    // 서식 문자 예시
    	System.out.printf("%20d\n", 2000);
    	System.out.printf("%-10s : %d\n","price",15000);
    	System.out.printf("%-10s : %d\n","income",200);
    	
    	System.out.printf("%-10s : %7d\n","price",15000);
    	System.out.printf("%-10s : %7d\n","income",200);
    	
    	System.out.printf("%02d\n" ,1);
    	System.out.printf("%02d\n" ,11);
    	
    	System.out.printf("%+d\n",-10);
    	System.out.printf("%+d\n",10);
    
    	System.out.printf("%.3f\n",123.1234567);
    	System.out.printf("%.2f\n",123.1234567);
    	System.out.printf("%.1f\n",123.1234567);
    	System.out.printf("%.0f\n",123.1234567);
    
    /*	결과
                    2000
    price      : 15000
    income     : 200
    
    price      :   15000
    income     :     200
    
    01
    11
    
    -10
    +10
    
    123.123
    123.12
    123.1
    123
    */
    ```


