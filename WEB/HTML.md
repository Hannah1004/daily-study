# HTML

[TOC]



### ※ HTML이란

- HyperText Markup Language

- 웹 페이지의 생김새를 묘사하는 마크업 언어

- HTML로 작성한 코드를 웹브라우저가 해석하여 사용자에게 보여준다.

- 마크업 언어 : 여는 태그와 닫는 태글로 영역을 표시하는 언어(XML, HTML)

- 웹 브라우저 : Chrome, IE, Safari, .. 등

  http 프로토콜을 이용하여 서버에 접속하고, 

  웹 서버에서 받아온 HTML코드를 해석해주는 프로그램

- HTML에서는 여러개의 공백도 하나로 인식하고, 

  Enter도 하나의 공백으로 인식한다.

##### #HTML의 기본 구조

```html
<!-- html의 주석 -->
<html> <!-- html : html 문서 영역을 표시하는 태그 -->
    <head> <!-- head : html의 설정 영역을 지정하는 태그 -->
        <!-- title에 적으면 웹 브라우저 탭에 나온다.-->
        <title>페이지의 제목을 정하는 곳</title>
    </head>
    <body> <!-- body : 현재 웹 페이지의 화면에 보여지는 내용을 채우는 곳-->
        
    </body>
</html>
```



### ※ 제목과 문단

- &lt;h1&gt;~&lt;h6&gt;까지의 태그 (heading tag)
  - &lt;&gt;는 html에서 태그를 의미하므로 `&lt;와 &gt;로`작성 해주어야 한다.
  - h1이 제일 큰 제목태그이고, 숫자가 커질수록 작은 제목 태그이다.
- &lt;p&gt;태그는 제목에 해당하는 문단이다.

##### # 블록 요소 (Block Elements)

- 제목태그(&lt;h&gt;)와 문단 태그(&lt;p&gt;)는 블록요소입니다.
- &lt;bt&gt;를 쓰지 않아도 줄이 자동으로 바뀐다.
- 새로운 영역을 지정하고 싶을 때 주로 새로운 블록 요소를 추가한다.

##### # 인라인 요소 (Inline Elements)

- 대표적으로 &lt;b&gt;태그, &lt;i&gt;는 인라인 요소입니다.
  - &lt;b&gt;태그 : 굵게, &lt;i&gt;태그 : 이탤릭체
- &lt;br&gt;태그를 사용하지 않으면 줄이 바뀌지 않는다.
- 새로운 영역을 지정하지 않으면 범위를 지정할 때 사용합니다.



### ※ 요소와 속성

##### #HTML 요소 (Element)

- &lt;tag&gt;content(innerHTML)&lt;/tag&gt;
- 여는 태그(&lt;&gt;)와 닫는 태그와 그 사이의 내용을 모두 통틀어서 HTML요소라고 부른다.
- br, hr처럼 닫는 태그를 생략 가능한 태그들도 존재한다.

##### # HTML 속성 (Attribute)

- 속성을 통해 해당 요소에 대한 추가적인 정보를 묘사할 수 있다.
- 대부분의 속성은 속성 이름과 속성 값이 짝을 이룬다.
- 속성은 반드시 해당 요소의 여는 태그(&lt;)에 정의해야 한다.
- 모든 요소는 속성을 가질 수 있다.
- ex: <b style="color: orange;">b의 여는 태그에 글자색을 orange색으로 속성을 줌<b>



### ※ HTML을 구성하는 언어들

##### # 웹 페이지를 구성하는 3가지 언어

- html : 웹 페이지의 뼈대를 담당하는 마크업 언어

- css : 웹 페이지의 디자인을 담당하는 스타일 시트 언어

- javascript : 웹 페이지의 동작을 담당하는 프로그래밍 언어, 웹 브라우저가 해석한다.

- css 예시

  ```html
  <style>
      /* css 주석 */
  	/* style 태그의 내부는 css 스타일 시트를 정의할 수 있는 영역 */
  	#para01{
      	background-color: red;
      	color: white;
      	padding: 30px;
  	}
  </style>
  ```

- javascript 예시

  ```html
  <p id="para01">
      문단
  </p>
  <script>
  	/* 자바스크립트 주석 */
      // Javascript 영역
      var para01 = document.getElementById("para01");
      para01.onmouseover = onmouseOverEvent;
      para01.onmouseleave = onmouseleaveEvent;
      
      function onmouseOverEvent(){
          para01.style.backgroundColor = "greenyellow";
          function onmouseleaveEvent(){
              para01.style.backgroundColor = "darkred";
          }
      }
  </script>
  ```



### ※ 링크

- &lt;a&gt;태그로 링크 걸기

- 자바 스크립트로 링크 걸기

##### # 외부 페이지로 링크 걸기

- &lt;a href="http://naver.com"&gt;네이버로 이동&lt;/a&gt;

##### # URL경로 올바르게 지정하기

- &lt;a href="../../assets/image/penguin.jpeg"&gt;
  - 앞에 ./ 또는 아무것도 안적으면 상대 경로가 된다.
- &lt;a href="/abcd"&gt;
  - 앞이 /로 시작하는 URL은 해당 도메인 루트(뿌리)에서 시작하는 경로가 된다.
- &lt;a href="//naver.com"&gt;
  - 앞이 //로 시작하는 경로는 프로토콜만 그대로 유지한 경로가 된다.

##### # 내부 페이지로 링크 걸기

- &lt;a href="C:\SpringEdu\Web Front\html\05_링크.html"&gt;
  - 5번 파일 보기 (1)
- &lt;a href="./05_링크.html"&gt;
  - 5번 파일보기 (2)

##### # 페이지의 특정 부분(ID)으로 링크 걸기

```html
<a href="#chap01">Chap 01.</a><br>
<a href="#chap02">Chap 02.</a><br>
<a href="#chap03">Chap 03.</a><br>

<h1 id="chap01">Chapter 01.</h1>
<p>This is paragraph</p>
<p>This is paragraph</p>

<h1 id="chap01">Chapter 02.</h1>
<p>This is paragraph</p>
<p>This is paragraph</p>

<h1 id="chap01">Chapter 03.</h1>
<p>This is paragraph</p>
<p>This is paragraph</p>
```

##### # 자바스크립트로 링크 걸기

- 자바스크립트를 통해 다른 페이지로 이동할 때는 location.href 값을 수정한다.

  &lt;div style="cursor: pointer;" onclick="location.href='http://naver.com';"&gt;자바스크립트 링크!&lt;/div&gt;



### ※ 이미지

##### # 웹 페이지에 이미지 넣기

- 이미지도 줄이 바뀌지 않는 인라인 요소이다.

- scr : 출력하고자 하는 이미지의 경로 (외부 또는 내부)

- alt : 해당 이미지에 대한 설명 (이미지 출력 실패시 대신 출력됨)

  ※ alt : 속성은 화면 읽어주는 프로그램이 이미지를 읽을 때 사용한다.

- width : 해당 이미지의 너비 설정

- height : 해당 이미지의 높이 설정

  ※ width/height는 둘 중 하나만 수정하면 비율을 자동으로 조절한다.

```html
<img src="인터넷에서 가져온 이미지 주소" alt="펭귄사진1" width="100" height="100">
<img src="../../assets/image/penguin.jpeg" alt="펭귄사진2">
```



### ※ 테이블

##### # 웹 페이지에 표 출력하기

- &lt;table&gt; : 표의 범위를 나타내는 태그
- &lt;tr&gt; : table row. 표에 한 행을 추가한다.
- &lt;th&gt; : table header. 행에 제목칸을 추가한다.
- &lt;td&gt; : table data. 행에 데이터 칸을 추가한다.

ex : 

<table border="3">
    <tr>
    	<th>이름</th>
        <th>주소</th>
        <th colspan="2">전화번호</th>
    </tr>
    <tr>
        <td>짱구</td>
        <td rowspan="2">서울시 송파구 잠실동</td>
        <td>1600-1111</td>
        <td>1111-1111</td>
    </tr>
    <tr>
    	<td>철수</td>
        <td>1600-1111</td>
        <td>2222-2222</td>
    </tr>
</table>

```html
<table border="3">
    <tr>
    	<th>이름</th>
        <th>주소</th>
        <th colspan="2">전화번호</th>
    </tr>
    <tr>
        <td>짱구</td>
        <td rowspan="2">서울시 송파구 잠실동</td>
        <td>1600-1111</td>
        <td>1111-1111</td>
    </tr>
    <tr>
    	<td>철수</td>
        <td>1600-1111</td>
        <td>2222-2222</td>
    </tr>
</table>
```



### ※ 리스트

##### # 순서 없는 리스트(unordered list)

- type : disc, circle, square, none
- &lt;ul&gt;&lt;/ut&gt; :unordered list
- 