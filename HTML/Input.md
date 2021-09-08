# input tag 의 type 들
- form 태그 에서 설명 했던 부분이라 중복되지만 확실히 알기 위해 예제 까지 연습해 본다.
1. input type = "text", input type = "password"
2. input type = "radio"
3. input type = "checkbox"
4. select option
5. input type = "button", input type = "submit", input type = "reset"
6. input type = "image"
7. input type = "file"
  
    
      
        
## 1. input type="text" , input type="password"
```HTML
name : <input type="text" name="my_name" size="20">
password : <input type="password" name="my_password" size="20">

<input type="text" name="my_name" size="20" value="수정불가" readonly>
```

## 2. input type = "radio"
```HTML
<input type="radio" name="food" value="chicken" checked> chicken
<input type="radio" name="food" value="pizza"> pizza
<input type="radio" name="food" value="pasta"> pasta
<input type="radio" name="food" value="salad"> salad
```

## 3. input type = "checkbox"
```HTML
<input type="checkbox" name="computer" value="CPU" checked> CPU
<input type="checkbox" name="computer" value="Memory"> Memory
<input type="checkbox" name="computer" value="HDD"> HDD
<input type="checkbox" name="computer" value="CD_ROM"> CD_ROM
<input type="checkbox" name="computer" value="GRAPHIC_CARD"> GRAPHIC_CARD
```

## 4. select option
```HTML
<table>
  <tr>
    <td colspan="2">
      <h2>  Favorite Language </h2>
    </td>
  <tr>
    <td valgn="top">
      <select name="language1">
        <option value="JavaSctipt">JavaScript</option>
        <option value="Java">Java</option>
        <option value="Python">Python</option>
      </select>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <select name="language2" size="3">
        <option value="JavaSctipt">JavaScript</option>
        <option value="Java">Java</option>
        <option value="Python">Python</option>
      </select>
    </td>
  </tr>
</table>
```

## 5. input type="button" , input type="submit", input type="reset"
```HTML
<input type="button" value="Login">
<input type="submit" value="Join">
<input type="reset" value="reset">
```

## 6. input type="image"
```HTML
Image:<input type="image" src="zder.jpg">
```

## 7. input type="file"
```HTML
FileName:<input type="file" name="filename">
```
