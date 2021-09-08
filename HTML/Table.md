# table 의 속성들
```HTML
<table>   : 테이블(표)을 만든다.
<tr>      : 테이블의 행(가로 한줄) 을 만든다.
<td>      : 테이블의 열 을 만든다. 내용이 들어가는 셀
<th>      : 테이블(표) 의 헤드 부분(자동으로 가운데 정렬, 굵게 적용), 열의 제목이 들어가는 셀
<caption> : 테이블의 이름을 표시
<thead>   : 테이블의 헤더 영역을 지정
<tbody>   : 테이블의 바디 영역을 지정
<tfoot>   : 테이블의 꼬리 영역을 
```
## 위 내용을 가지고 만년달력을 작성 해 보겠다.

```HTML
<table
       border="1"
       width="75%"
       height="500"
       cellspacing="1">
  <caption> 월 </caption>
  <thead>
    <tr align="center" bgcolor="white">
      <th>일</th>
      <th>월</th>
      <th>화</th>
      <th>수</th>
      <th>목</th>
      <th>금</th>
      <th>토</th>
    </tr>
  </thead>
  
  <tbody>
    <tr align="center" bgcolor="white">
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    
    <tr align="center" bgcolor="white">
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    
    <tr align="center" bgcolor="white">
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    
    <tr align="center" bgcolor="white">
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    
    <tr align="center" bgcolor="white">
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
     </tr>
  </tbody>
```
## `속성`들을 살펴보자
```HTML
align       : 정렬을 지정한다.(left, center, right)
border      : 테두리 선의 두께를 지정한다.
bgcolor     : 배경색을 지정한다.( 색은 기존의 정의 되어 있는 색("green", "black")과, RGB 형식(#000000)의 색으로도 지정할 수 있다.
bordercolor : 테두리 선의 색을 지정한다. 색을 지정하는 방법은 bgcolor 와 동일하다.
cellspacing : 셀의 간격을 지정한다.
width       : 가로길이(넓이)를 지정한다.(상수값을 입력할 수도, % 단위로 입력할 수도 있다. 다만 %를 사용할 때는 웹브라우저 크기에 대한 % 이다.)
height      : 세로길이(높이)를 지정한다.
rawspan     : 지정한 값 만큼 행을 병합한다.(위아래로)
colspan     : 지정한 값 만큼 열을 병합한다.(좌우로)
```
## rawspan 과 colspan
```HTML
<table
       border="1"
       width="50%"
       height="200"
       cellspacing="1">
 <tr align="center" bgcolor="white">
  <td rawspan="2"> rawspan 사용 </td>
  <td></td>
  <td></td>
  <td></td>
 </tr>
 <tr align="center" bgcolor="white">
  <td></td>
  <td></td>
  <td></td>
 </tr> 
 <tr align="center" bgcolor="white">
  <td colspan="4"> colspan 사용 </td>
       </tr>
</table>
```
- `<table>` 을 사용하여 테이블을 만든다.
- `<tr>` 태그를 사용하여서 하나의 행을 만든다.
- `<tr>` 태그로 행을 만들었으면 그 안에 `<td>` 를 사용하여서 열을 나누어 준다.
- `<td>` 의 개수는 모든 `<tr>` 에서 동일한 것이 좋다. 만약 값을 비워야 하면 `<td>` 로 열을 만들고 값을 넣지 않으면 된다.
