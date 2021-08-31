- # Object(객체)
    
  - Javascript 는 객체를 기반으로 하는 Script 언어이다. 그리고 Javascript 를 이루고 있는 거의 대부분은 Object(객체)이다.
  - Object(객체)란 여러 속성을 하나의 변수에 저장할 수 있도록 해주는 Data Type(데이터 타입) 이며, Key 와 Value 구조로 되어 있다.
   
- ## 객체의 특징
   
1. Object(객체)는 중괄호 표기 { } 를 이용하여 생성한다.
  ```javascript
  const user = {Object(객체)};
  ```
2. Object(객체)는 각각 Key 와 Value 구조로 입력한다. 
  ```javascript
  const user = {
          ㄴVariable(변수)
    name : '호순'
    ㄴKey:  ㄴValue
  };
  ```
3. Object(객체)의 값은 properties(속성) 이라고 한다.
4. Key 는 문자열 또는 기호 로 생성한다. Value 는 어떤 유형이어도 상관 없다.
5. 객체는 각각 Key 와 Value 구조로 입력하되 구분할 때는 ,(쉼표) 로 구분한다.
```javascript
  const user = {
    firstname : '호순' ,
    lastname : '문' ,
    age : 6 ,
    height : 184
  };
  ```
6. Variable(변수)는 예약어의 이름을 가질 수 없으나, Object(객체)는 어떤 이름도 상관 없다.
```javascript
// *는 ES6에서 추가된 예약어
abstract
arguments 
boolean 
break 
byte
case  
catch 
char  
class*  
const
continue  
debugger  
default 
delete  
do
double  
else  
enum* 
eval 
export*
extends*  
false 
final 
finally 
float
for 
function  
goto  
if  
implements
import* 
in  
instanceof  
int 
interface
let 
long  
native  
new 
null
package 
private 
protected 
public  
return
short 
static  
super*  
switch  
synchronized
this  
throw 
throws  
transient 
true
try 
typeof  
var 
void  
volatile
while 
with  
yield
```
8. Object(객체)는 Variable(변수)이다. 그러나 Object(객체)에는 많은 값이 포함될 수 있다. (단일 값도 포함 할 수 있다.)
9. Object(객체) Variable(변수), (=객체변수) 를 복사하면 Reference(참조) 가 복사되고 Object(객체) 가 복사되지 않는다.
```javascript
    const user = { name : '문호순'};
    mother = user;  // copy the reference
```
- ## 객체의 종류
    - 배열 (Array)
    - 함수
    - 객체 (Object)
    - 날짜 (Date)
    - 수학 (Math)
    - 정규식표현
    - Boolean(new keyword로 정의된 경우)
    - 숫자(number) (new keyword로 정의된 경우)
    - 문자열(String) (new keyword로 정의된 경우) 
    - Javascript 에서 원시값을 제외한 모든 Javascript 값은 객체 이다.<br>
       `` 
       원시값 : 어떤 특성 또는 방법이 없는 값
       ``
       <br>
       ``
       기본 데이터 형식 : 원시 값을 갖는 데이터
       ``
       <br>
- #### 객체가 아닌 기본 데이터 유형
    - String
    - number
    - boolean
    - null
    - undefined

- ## Javascript 의 객체 구성
    ### 1. Javascript 내장 객체(Built-in Object)
    Javascript 엔진이 구동될 때 즉시 제공되며, Javascript 코드 어디에든 사용이 가능하다. 아래 내장 객체들 외에도 많은 내장 객체들이 있다.
    - Array
    - Object
    - String
    - Number
    - Math
    - Date
    - Global
    - Boolean
    
    ### 2. 브라우저 내장 객체 (Native Object)
    브라우저 내장 객체도 Javascript 가 구동 될때 바로 사용 가능한 내장 객체다. 그러나 브라우저(Chrome, Safari, FireFox, Edge 등등..)
    에서 내장 객체를 사용 할 때, 브라우저 마다 구성을 다르게 하는 경우가 있다. 그래서 Javascript 내장 객체와 따로 적어 두었다.
    하지만, 브라우저 내장 객체는 Javascript 엔진을 구동하는 하면서 build 가 되는 객체 들이다. 예 로는 `BOM` 과 `DOM` 이 있다.
    이 객체들은 Javascript 내장 객체가 구성이 되고 난 후에 구성이 된다.
    <br>
    ```
    BOM(Brouser Object Model 의 약자)
      - 브라우저에 대한 모든 내용을 담고있는 객체. 브라우저에 관련 된 내용 모두
      - 뒤로가기, 북마크, 즐겨찾기, 히스토리, URL정보 등등..
      - 브라우저가 가지고 있는 정보를 따로 객체화 시켜서 관리함
    ```
    ```
    DOM(Document Object Model 의 약자)
      - 문서에 대한 모든 내용을 담고있는 객체. 도큐먼트에 관련 된 내용 모두
      - 문서 즉 열려진 페이지에 대한 정보를 따로 객체화 시켜서 관리함
    ```
    ### 2. 사용자 정의 객체 (Host Object)
    사용자가 생성한 객체이다. 생성자 함수 또는 객체 리터럴을 통해 사용자가 객체를 정의 하고 확장시킨 객체들이기 때문에 
    내장 객체들이 구성된 후에 구성 된다.
    
    











<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
- 참조<br>
    - https://velog.io/@surim014/series/JavaScript<br>
    - https://m.blog.naver.com/PostList.naver?blogId=magnking<br>
    - https://kevinthegrey.tistory.com/
