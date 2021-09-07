# HTML 의 a tag 와 속성 및 사용법
1. href : 연결할 페이지의 주소를 지정 한다.
```HTML
<a href="http://www.github.com/bigveloper"> bigveloper 의 github 로 이동하기 </a>
```
`<a>` tag 의 주소는 다양한 방법으로 지정 할 수 있다.
```HTML
<!-- 절대경로 URL : 링크의 전체 경로 -->
<a href="http://www.github.com/bigveloper"> bigveloper 의 github 로 이동하기 </a>

<!-- 상대경로 URL : 같은 프로젝트 폴더 내의 경로 -->
<a href="main.html"> 메인으로 바로가기 </a>
<a href="/user/detail.html"> 사용자 정보 상세보기 </a>

<!-- element ID 를 이용한 URL : 같은 문서 내의 엘리먼트ID -->
<div id="copyright">copyright</div> 로 div 엘레멘트 ID 를 지정
<a href="#copyright">copyright 로 이동하기 </a>

<!-- JavaScript 함수 호출 -->
<a href="javascript('알림');">알림</a>

<!-- 기타 -->
<a href="ftp://ftp:test.com">go to ftp</a>
<a href="mailto:test.gmail.com"> send mail</a>
```
