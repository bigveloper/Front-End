# <form ...>....</form> 태그 정리
 - form 은 컨트롤 요소(control elelment) 로 구성된다. `text`, `button`, `radio` 등이 `control` 이다.  
    - name :  form 의 이름, 서버로 보내질 때 이름의 값으로 데이터 전송
    - action : form 이 전송되는 url 또는 html 링크
    - method : 전송 방법 설정, `get = default`, `post = 데이터를 url 에 공개하지 않고` 숨겨서 전송 하는 방법
    - autocomplete : 자동완성, `on` 으로 하면 `form 전체 자동 완성` 허용

```HTML
 <form name="profile" action="/action_page.php" method="get" autocomplete="on">
  <input type="text" name="id" />
  <select>
   <option value="blue">
  </select>
 </form>
```
  
## <form> 내부의 태그와 속성들
 1. <input> 태그
  type : 입력 형식  
  name : 서버로 전송되는 데이터 이름
  - text 입력란 `<input type="text">`
 ```HTML
 text: <input type:"text" name="id" value="기본값" />
 ```  
   
  - password 입력란(입력한 내용이 보이지 않음) `<input type="password">
 ```HTML
 password: <input type="password" name="pwd" placeholder="PASSWORD">
 <!-- placeholder 는 기본적으로 input 안에서 내용을 보여준다. 여기서는 PASSWORD 를 보여준다.  -->
 ```  
   
 
 - button `<input type="button">`
 ```HTML
 <input type="button" value="전송" onclick="alert('hello world')">
 <!-- onclick 은 button 을 누르게 되면 실행되는 것  -->
 ```  
   
   
 - submit 서버로 form 에 입력한 데이터를 보내주는 button `<input thpe="submit">`
 ```HTML
 <input type="submit" value="제출하기">
 ```  
   
   
 - radio 단일선택 `<input type="radio">`
 ```HTML
 <h4>radio</h4>
 <input type="radio" name="color" value="red"> 빨간색 <br>
 <input type="radio" name="color" value="blue" checked> 파란색
 ```
