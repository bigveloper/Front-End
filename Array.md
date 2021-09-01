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

- ## Array(배열) 고차 함수
 - ### filter
  - filter 메소드는 주어진 함수의 내용에 해당하는 모든 요소를 모아 `새로운 배열`로 반환 한다.
```javascript
const cities = ['Seoul', 'London', 'HongKong', 'Newyork', 'shanghai'];
const result = cities.filter(city => city.length <= 6);
console.log(result);
  
// [ 'Seoul', 'London' ]
```
변수 cities 안에 배열로 담은 문자들 중 길이가 6 과 같거나 작은 것들을 골라서 `새로운 배열`로 모두 반환 했다.<br>

 - ### find
  - find 메소드는 주어진 함수를 만족하는 `첫번째 요소` 의 값을 반환 한다. 해당되는 요소가 없으면 undefined 를 반환 한다.
```javascript
const friends = [
  {
    name: '호순' ,
    age: 36 ,
    job: 'developer' ,
    married : false,
  },
  {
    name: '한순' ,
    age: 36 ,
    job: 'CEO' ,
    married : true,
  },
  {
    name: '의순' ,
    age: 36 ,
    job: 'developer' ,
    married : false,
  }
];
const findSadGuy = friends.find((friends) =>  {
  return friends.married===true;
});

console.log('슬픈놈', findSadGuy);

// 슬픈놈 { name: '한순', age: 36, job: 'CEO', married: true }
```
변수 friends 안에 배열에 담은 객체들 중 key 이름이 married 이고 value 가 true 인 요소를 찾아서 반환 했다.<br>

여기까지 이해 했다면, `filter()` 와 `find()` 의 역할이 비슷하다고 생각할 수 있다.<br>
그러나 아래 코드를 살펴보면, 다르다는 것을 알 수 있다.
```javascript
const arr = [10, 20, 30, 40, 50];

const result = arr.find(item => item>30);
console.log('find() 사용');
console.log(result);

// 40

const result2 = arr.filter(item => item>30);
console.log('filter() 사용');
console.log(result2);

// [ 40, 50 ]
```
같은 조건 이지만, `filter()` 경우에는 조건에 해당하는 `모든 요소` 를 **골라서** 반환 했다.<br>
그러나 `find()` 경우에는 조건에 해당하는 `첫 요소` **만** 가져왔다.<br>
`filter()` 가 함수의 특정 조건에 맞는 값들을 모두 걸러서 반환 해줬다면,<br>
`find()`는 함수의 특정 조건에 맞는 값이 나오면 그 값만 걸러서 반환 해줬다.
<br><br>
명심하자 `백문이 불여일타` 이다.
<br>

  - ### map
   - map 메소드는 Array(배열) 내부의 모든 각각의 요소에 대하여 주어진 함수를 실행한 결과를 모아서 `새로운 배열`로 반환 한다. 
```javascript
const numbers = [2, 4, 6, 8];
const mapNum = numbers.map(x => x*2);
console.log(mapNum);

// [ 4, 8, 12, 16 ]
```
변수 numbers 안에 Array(배열) 로 담은 숫자로 된 요소들을 map 메소드 안 x 에 담고 화살표 함수를 통해<br>
곱하기 2 를 각각 하여 `새로운 배열`로 반환 하였다. 여기서 우리가 더 정확히 알아야 할 부분이 있다.<br>
<br>
map 메소드는 callbackFunction 을 실행한 결과를 가지고 새로운 배열을 만들 때 사용한다.
`array.map(callbackFunction(currentValue, index, array), thisArg)`
여기서 보면,<br>
callbackFunction 은 currentValue, index, array 3개의 매개변수를 갖는다.<br>
currentValue : 배열 내 현재 값<br>
index : 배열 내 현재 값의 인덱스<br>
array : 현재 배열<br><br>

예를 들어보자면,
```javascript
const testArray = [1,2,3,4,5];
const returnArray = testArray.map(function(currentValue, index, array){
  console.log(currentValue);
  console.log(index);
  console.log(array);
    return currentValue*2;
 });
    console.log(returnArray);
    
// 결과
1
0
[ 1, 2, 3, 4, 5 ]
2
1
[ 1, 2, 3, 4, 5 ]
3
2
[ 1, 2, 3, 4, 5 ]
4
3
[ 1, 2, 3, 4, 5 ]
5
4
[ 1, 2, 3, 4, 5 ]
[ 2, 4, 6, 8, 10 ]
```
이 내용을 보고 이해 했으면 하는 바람이다. 나는 도움을 얻어 어느정도 이해 했지만...<br>
추후 더 이해하기 쉽도록 업데이트 하겠다.
 
  - ## push
  
  - ## concat
      
  - ## sum
  
  - ## every

  - ## reduce 

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
- 참고<br>
https://velog.io/@surim014<br>
https://helloworldjavascript.net/pages/190-array.html<br>
https://freestrokes.tistory.com/

