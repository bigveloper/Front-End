  - # React 에서 알아야 할 push() 와 concat()
  
  - ## push
   - push() 메소드는 Array(배열) 요소 끝에 `요소`를 `추가` 한다.<br>
empty Array 에 내용을 추가할 수 있다.

```javascript
const arr = [1];
arr.push(2);
arr.push(3);
arr.push(4);


console.log(arr);

// [ 1, 2, 3, 4 ]
```
<br>
변수 arr 에 배열 요소로 숫자 1이 들어가 있고, push() 메소드를 통해 각각의 요소들을 변수 arr 에 넣었더니 모든 요소들이 합쳐져서 배열로 반환 되었다.<br>
그러나, 기존 변수 arr 의 요소들이 손상(변경) 되었다.<br>

- ## concat
  - concat() 메소드는 배열이나, 값들을 기존의 배열에 `합쳐서 새로운 배열` 로 반환 한다.
```javascript
const arr = [1];
const arr1 = [2];
const arr2 = [3];
const arr3 = [4];
const newArr = arrNew.concat(arr1, arr2, arr3);

console.log(newArr);
console.log(arr);
console.log(arr1);

// [ 1, 2, 3, 4 ]
// [ 1 ]
// [ 2 ]
```
각 배열이 들어 있는 변수를 newArr 이라는 변수에 concat() 메소드를 통해 각 배열이 들어있는 변수를 호출하니 각 배열의 요소들이 합쳐져서 반환 되었다.<br>
그러나, 기존 변수의 요소는 손상되지 않았다.<br>

- React 에서 JavaScript 메소드인 push 와 concat 을 다시 설명하는 이유가 있다. 이 부분은 React 코드를 추가해 추후 다시 설명하겠지만,<br>
React 의 경우에는 useState 라는 Hook 을 통해서 state 를 사용하는데, 이 state 에 새로운 요소를 추가 할 경우,<br>
`push()` 와 같은 `기존 요소를 변경`하는 메소드는 사용하지 않는 것이 좋다. `concat()` 처럼 새로운 요소를 추가 할때,<br>
`기존요소를 변경하지 않는` 메소드를 사용하는 것이 좋다.(성능을 개선할 때 편하고 좋다.)<br>
<br>
물론, 꼭 이렇게 해야 한다. 는 아니다.
      
