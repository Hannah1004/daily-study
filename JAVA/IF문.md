# IF문

### # if문

- ()안의 값이 true일 때 {}안의 내용을 실행
- ()안의 값이 false일 때 {}안의 내용을 무시
- {}안에서 실행할 내용이 단 한줄이라면 {}을 생략할 수있다.



### # else if문

- 위에 있는 if문이 실행되지 않았다면 밑에서 if문처럼 동작
- else if는 단독으로 사용 불가
- esle if는 여러번 사용 가능



### # else문

- 위에 있는 if문과 else if문이 모두 실행 되지 않았다면 {}안의 내용을 무조건 실행
- if문 바로 다음에 사용할 수도 있다.
- 단독으로 사용 불가



##### 예시

```java
char ch = "h";

if(ch >= '가' && ch <= '힣'){
    System.out.println("ch에 들어있는 값은 한글입니다.");
} else if(ch >= 'a' && ch <= 'z'){
    System.out.println("ch에 들어있는 값은 소문자입니다.");
} else if(ch >= 'A' && ch <= 'Z'){
    System.out.println("ch에 들어있는 값은 대문자입니다.");
} else {
    System.out.println("ch에 들어있는 값은 알파벳도 한글도 아닙니다");
}

// 결과 : ch에 들어있는 값은 소문자입니다.
```

