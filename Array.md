- # Array
`Array(배열)` 은 `하나의 변수` 에 `여러 개의 값` 을 `순차적으로 저장` 할 때 사용 한다.
``` javascript
const empty = []; // Empty Array
const numbers = [ 1,2,3,4 ]; // Number Array
const strings = [ '호순', '용순', '삼순' ]; // String Array
const object = [ {name: '호순'}, {name: '용순'}, {name: '삼순'} ]; // Object Array
const mixed = [ 1, '호순', {name: '용순'}, null} ]; // 숫자, 문자, 객체, null 도 Array 안에 담을 수 있다.
```
- Array(배열) 안에 들어있는 값들을 `요소`(element, item, etc) 라고 한다.<br>
- Array(배열)의 값은 어떤 값이라도 Array(배열)의 요소로 추가할 수 있고, `type` 이 다른 값들도 함께 담을 수 있다.

- ## Array(배열)의 특징
 - Array(배열)은 번호를 가진 인덱스를 갖는 특별한 유형의 `객체` 이다. (객체 지만, 객체 라고 하기엔 `접근방법` 자체가 __다르다__.) 
``` javascript
// Array 
const names = [ '호순', '용순', '삼순' ];
names[0];
// 결과 : 호순

// Object
const names = { first : '호순', second : '용순', third : '삼순' };
names.first;
// 결과 : 호순
```
 - Array(배열) 안의 `요소` 는 `객체` 가 될 수 있다.
 - 동일한 Array(배열)에 `다른유형의 변수` 를 가질 수 있다.
 - Array(배열) 에 `객체` 를 가질 수 있다.
 - Array(배열) 에 `함수` 를 가질 수 있다.
 - Array(배열) 에 Array(배열) 를 가질 수 있다. (`다차원 Array(배열)`) 
 ```javascript
 nameArray[0] = Moon;
 nameArray[1] = Jang;
 nameArray[2] = Kim;
 ```
- ## Array(배열) 과 Object(객체) 의 차이점
  - Array(배열)은 숫자로 이루어진 index(인덱스)를 사용한다.
  - Object(객체)는 이름으로 이루어진 index(인덱스)를 사용한다.
 
- ## Array(배열) 과 Object(객체) 의 각각 사용시기
  - Javascript 는 Array(배열) 에서 이름으로 된 index(인덱스)를 지원하지 않는다.
  - 요소(`배열 안의 값`) 이름이 `String(문자열)`이 되도록 하려면 `Object(객체)`를 사용 한다.
  - 요소 이름을 `Number(숫자)` 로 하려면 `Array(배열)` 을 사용 한다.
  - 요소들의 `정렬` 이 필요할 경우 `Array(배열)` 을 사용한다.

- ## Array(배열) 사용시 주의 할 점
```javascript
const names = new Array('호순', '용순', '삼순', '사순', '오순');    // X
const names = ['호순', '용순', '삼순', '사순', '오순'];             // O
```
  - 생성자 `new Array()` 보다 대괄호 `[ ]` 를 사용하자

- ## Array(배열) 을 확인하는 방법
  
  - ## filter
  
  - ## find
  
  - ## push
  
  - ## concat
  
  - ## map
  
  - ## sum
  
  - ## every

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
- 참고<br>
https://velog.io/@surim014<br>
https://helloworldjavascript.net/pages/190-array.html

