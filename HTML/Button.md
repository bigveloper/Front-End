# <button>...</button> tag 
button 의 type 은 크게 3 종류로 나누어 진다.  
종류로는 button / submit / reset 이 있다. 이 3 종류의 버튼 타입의 기능에 대하여 알아보자

- button  
`<button> 버튼 </button>`
버튼이 브라우저 창에 생겨나고, 클릭해도 아무런 기능은 없다.  
이와 같은 button 은 자바스크립트와 같은 다른 언어의 함수 및 기능을 구현 해야 한다.
`<button id="a" type="button"> 버튼 </button>`  
  
- submit  
submit 은 `<input type="submit">` 과 동일한 기능을 수행한다.  
`서버로 데이터를 전달하는` 역할을 하는 type 이다. 참고로 아무 타입 지정 없이  
`<button> 버튼 </button>` 을 설정해도 button 의 기본 default 값이 submit 이기 때문에 아래의 코드와 같은 기능을 한다.  
`<button id = "b" type = "submit" value="내용전달"> 버튼 </button>`  
  
- reset  
type 이름에서도 느껴지듯이 button 을 감싸고 있는 form 데이터의 입력된 데이터를 초기화 하는 type 이다.  
`<button id = "c" type = "reset" value = "내용초기화"> 버튼 </button>  
  
    
    
```HTML
<!DOCTYPE html>
<html>
  <head>
  <meta charset="utf8">
  <title> button tag </title>
  <style type ="text/css">
    
    #a {
        background: red;
        color: #fff;
    }
    #b {
        background: black;
        color: #fff;
    }
    #c {
        background: green;
        color: #fff;
    }
    
  </style>
    
  <body>
  <form action="#" method="get">
  <br><br>
    <label for="content"> 테스트 내용: </label>
    <input type="text" id="content" name="content" /><br><br>
    
    <button id="a" type="button"> 버튼(button) </button>
    <button id="b" type="reset" value="내용초기화"> 버튼(reset) </button>
    <button id="c" type="submit" value="내용전달"> 버튼(submit) </button>
    
  </form>
  </body>
</html>
  ```
