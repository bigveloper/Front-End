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
그러나, 기존 변수 arr 의 요소들이 손상(변경) 되었다.
