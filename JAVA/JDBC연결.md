# JDBC

- Java와 DB연결해주기

##### ※ sqldeveloper에 jbcd에 lib에 ojdbc8.jar가 들어있다.

1. 연결해주고싶은 프로젝트를 우클릭

2.  buildPath -> configure buildpath(맨밑) 

3. libraries선택 -> addexternal jars선택(오른쪽에) -> ojdbc8.jar선택

4.  apply and close누름

5. referenced libraries에 ojdbc8.jar이 들어있으면 성공!

   **밑에 사진에서 설명**

![](C:\SpringEdu\daily-study\JAVA\image\ojdbc8위치.png)

![1626851130489](C:\SpringEdu\daily-study\JAVA\image\JDBC연결1.png)![1626851228267](C:\SpringEdu\daily-study\JAVA\image\JDBC연결2.png)