# Hook 에 대해서 알아보자
 - 모르면 Hook 간다.  
  
    
Hook 은 React 16.8 버전 부터 새로운 요소로 추가 되었다.  
Hook 을 이용하면 기존 Class 바탕의 코드를 작성할 필요 없이, 상태 값과 여러 React 기능을 사용할 수 있다.  
  
  먼저 `useState` 맛보기
```JavaScript
import React, {useState} from 'react' // 기능을 쓰려면 import 가 기본 

// component
function Example(){

// state
const [count, setCount] = useState(0); // [count = get(읽기) , setCount = set(쓰기)], 기본값으로 0이 들어가 있다.

// JSX(여기서는 <> 태그를 사용하여 HTML 처럼 화면에 보여줄 내용을 구성한다.)
return(
  <div>
    <p> You Clicked {count} times</p> // {count} 안에는 위 state 에서 선언해준 count 가 들어와서 보여주게 된다.
    <button onClick={() => setCount(count + 1)}> 
      Click Me
    </button>
  </div>
  );
}
// 클릭을 하면 위 setate 지역의 setCount 를 통해 count 에 +1 하는 명령을 수행한다. 
```

또한 `useState` 는 하나의 `component` 내에서 여러개의 `State Hook` 을 사용 가능하다.
```JavaScript
// component
function ExampleManyState(){
 
// state
 const [age, setAge] = useState(60) // 인생은 60부터, 60을 넣어줬다.
 const [fruit, setFruit] = useState('grape') // 딸이 포도를 좋아한다. 포도를 넣어줬다. 문자니까 '' 감싸서
 const [city, setCity] = useState('London') // 런던 가보고 싶으니까 런던 을 넣었다. 문자니까 '' 감싸서
 
 // event
 const onFruit = e => setFruit(e.target.fruit);
 const onCity = e => setCity(e.target.city);
 
// JSX
 return(
 <div>
 <p> 살고싶은 나이는 {age} </p>
 <button onClick={() => setAge(age + 1)}> 살고싶은만큼 Click </button>
 </hr>
 <p> 먹고싶은 과일은? </p>
 <input value = {fruit} Onchange = {onFruit} />
 </hr>
 <p> 가고싶은 도시는? </p>
 <input value = {city} Onchange = {onCity} />
 </div>
 );
}

export default ExampleManyState;
```
