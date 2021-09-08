# <form></form> 태그 정리
 - form 은 컨트롤 요소(control elelment) 로 구성된다. `text`, `button`, `radio` 등이 `control` 이다.  
    - name :  form 의 이름, 서버로 보내질 때 이름의 값으로 데이터 전송
    - action : form 이 전송되는 url 또는 html 링크
    - method : 전송 방법 설정, `get = default`, `post = 데이터를 url 에 공개하지 않고` 숨겨서 전송 하는 방법
    - autocomplete : 자동완성, `on` 으로 하면 `form 전체 자동 완성` 허용

```HTML
 <form name="profile" action="/action_page.php" method="get" autocomplete="on">
  <input type="text" name="id">
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
 text: <input type:"text" name="id" value="기본값">
 ```  
   
  - password 입력란(입력한 내용이 보이지 않음) `<input type="password">`
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
   
   
- checkbox 다중선택 `<input type="checkbox">`
```HTML
 <h4>radio</h4>
 <input type="checkbox" name="color" value="red"> red <br>
 <input type="checkbox" name="color" value="green" checked> green <br>
 <input type="checkbox" name="color" value="pink" checked> pink <br>
```  
   
   
- file upload `<input type="file">`  
 `method="post"` 일때만 가능하다.  
 `enctype`: form 데이터를 서버로 제출할 때 데어티가 인코딩 된 방법을 명시 한다.  
 `"multipart/form-data"`: 모든 문자를 인코딩하지 않음
```HTML
 <form action = "http://localhost/upload.php" method="post" enctype="mulipart/form-data">
  <input type = "file" name="selected=file">
  <input type = "submit">
 </form>
```  
   
   
 - hidden 눈에 보이지 않는 정보를 서버쪽으로 보낼 때 사용 한다. `<input type="hidden">`
```HTML
 <input type = "hidden" name = "hide" value = "superstar">
 
 <!-- superstar 를 서버로 전송 -->
 
```  
   
   
 2. <textarea> 태그
  - <textarea> 여러 줄의 텍스트를 입력할 때
```HTML
<form>
 <p> textarea : 
  <textarea cols="50" rows="3"
            placeholder="default">입력하세요.</textarea>
 </p>
</form>
```  
   
   
 3. select 태그  
  - 드롭 다운 형식의 선택, 선택 항목은 option 으로 사용 한다.  
```HTML
<form>  
 <select name = "color">  
  <option value="서버에 전송될 값"> red </option>  
  <option value="blue"> blue </option>  
 </select> 
 <!-- 다중 선택 multiple 추가 -->  
 <select name = "color2" multiple>  
  <option value="green"> green </option>  
  <option value="pink"> pink </option>  
 </select>  
</form> 
```  
</form>
   
 4. label 태그  
  - control 의 제목이 그것의 이름표라는 것을 명시하기 위해 사용  
  - checkbox 나 radio 에서 값을 클릭해도 표시될 수 있게 할 수 있음    
    (값이 radio의 label이라는 것을 표시해준다.)  
  - text 에서는 화면상에서 label 클릭하면 text 입력 창으로 커서가 간다.  
```HTML
 <form action="">  
  <p>  
   <label for ="name_txt"> text : </label>  
   <input id="name_txt" type="text" name="id" value="default">   
  </p>  
  <p>  
   <input id="color_pink1" type="radio" name="color" value="default">  
   <label for="color_pink1"> pink </label>  
   <input type="radio" name="color" value="default"> green  
  </p>  
 </form>
```
