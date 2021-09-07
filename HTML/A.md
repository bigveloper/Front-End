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
<div id="copyright"> copyright </div> 로 div 엘레멘트 ID 를 지정
<a href="#copyright"> copyright 로 이동하기 </a>

<!-- JavaScript 함수 호출 -->
<a href="javascript('알림');"> 알림 </a>

<!-- 기타 -->
<a href="ftp://ftp:test.com"> go to ftp </a>
<a href="mailto:test.gmail.com"> send mail </a>
```

2. target : link 를 click 할 때 창을 어떻게 열지 설정한다.  

`<a href="http://www.github.com/bigveloper" target="_blank"> bigveloper 의 github 로 이동하기 </a>`
  
```HTML
_self : 링크를 클릭한 해당 창에서 연다.
_blank : 링크를 새창으로 연다.
_parent : 부모 창에서 연다.(부모 창이 없으면 _self 속성으로 처리)
_top : 전체 브라우저 창에서 가장 상위의 창에서 연다.(부모 창이 없으면 _self 속성으로 처리)
```

3. title : 해당 링크에 마우스 커서를 올릴 때 도움말 설명을 설정한다.  

`<a href="http://www.github.com/bigveloper" title="bigveloper github"> bigveloper 의 github 로 이동하기 </a>`
