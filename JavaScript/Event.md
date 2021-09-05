# JavaScript Event 종류
- 기본 이벤트
  - 요소에 개발자가 굳이 이벤트를 연결하지 않았음에도 기본적으로 실행되는 이벤트
    - A 요소를 클릭 => 해당 경로로 페이지 이동
    - 브라우저 화면에서 우측 마우스 버튼 클릭 => ContextMenu 나타남
    - form 요소 내 submit 버튼을 클릭 => 지정된 경로로 내용을 전송함
  
- 마우스 이벤트
  - onclick : 마우스 버튼을 클릭하고 버튼에서 손을 뗌
  - ondbclick : 마우스 버튼을 더블 클릭 함
  - onmousedown : 마우스 버튼을 누른 상태
  - onmouseup : 마우스 버튼을 뗀 상태
  - onmouseout : 마우스 포인터가 요소 밖으로 벗어남
  - onmousemove : 마우스 포인터가 움직임
    - 마우스 커서가 해당 요소 안을 움직일 때 또는 커서 위치 확인에 유용하다.
  - contextMenu : 마우스 우측 클릭시, contextMenu 가 보이기 직전에 발생
  - mouseWheel event 등
    
- 키보드 이벤트
  - onkeydown : 키보드의 키를 누르는 순간
  - onkeyup : 키보드의 키를 눌렀다 떼는 순간
  - onkeypress : 키보드의 키를 눌러 문자가 연결 되었을 때
    - 곧, 화면에 글자가 완성 되는 경우만 이나 한편, 누르고 있는 동안 화면에 해당 키가 연달아 나타나듯 해당 이벤트도 계속 발생됨  
   
- 폼 이벤트
  - onsubmit : 폼 제출 버튼을 누름
    - 제출 / 전송 버튼을 누르거나 텍스트 필드에서 엔터키 를 누름
  - onreset : 폼을 초기화 하기 위함
  - onchange : 폼 필드에서 변경이 일어남
    - `input` 요소의 텍스트 변동, `radio` 버튼의 클릭 등 
  - onfocus : 웹브라우저가 특정 요소에 집중함
    - 해당 요소를 클릭, 마우스 커서를 놓을 때 등
  - onblur : focus 의 반대
    - 탭 누름, 필드 밖을 클릭 할 때 등 
  - onselect : 텍스트 필드 등의 텍스트를 선택 했을 때
  
- 문서 /  창 이벤트
  - onload : HTML 문서 및 추가 자원(이미지 등) 들을 `모두 불러 왔을 때` 발생
  - DOMContentLoaded : HTML 문서를 읽고 `DOM Tree 구축을 완료 할 때` 발생
    - 위 load 와 달리, 이미지 로드, 스타일시트 등을 기다리지 않고 바로 시작
  - onreadystatechange : XBR 프로퍼티 참조 http://www.ktword.co.kr/test/view/view.php?m_temp1=5949&id=1382
  - ontimeout
  - onresize : 요소 크기의 변동시
    - 창의 최대화 버튼 또는 창의 사이즈를 조절
  - onscroll : 페이지 스크롤 이동
    - 스크롤바를 드래그 하거나, 또는 키보드(위/아래/home/end 등) 또는 마우스 휠 사용 
  - onunload : 해당 페이지를 벗어남
    - 다른 페이지로의 링크를 클릭, 브라우저 탭/창을 닫음 등 
  
- 기타 이벤트
  - 텍스트 입력 이벤트
  - hashchange 이벤트 : 해쉬 변경시 이벤트 발생
    - [참고] : location 객체 참조 http://www.ktword.co.kr/test/view/view.php?m_temp1=5991&id=51
    - [참고] : MDN web docsm w3schools 참조
      - https://developer.mozilla.org/ko/docs/Web/API/WindowEventHandlers/onhashchange
      - https://www.w3schools.com/jsref/event_onhashchange.asp 
  - onerror : 에러 발생 이벤트

  

