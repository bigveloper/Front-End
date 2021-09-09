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
 const onFruit = e => setFruit(e.target.value);
 const onCity = e => setCity(e.target.value);
 
// JSX
 return(
 <div>
 <p> 살고싶은 나이는 {age} </p>
 <button onClick={() => setAge(age + 1)}> 살고싶은만큼 Click </button>
 </hr>
 <p> 먹고싶은 과일은? </p>
 <input value={fruit} onChange={onFruit} />
 </hr>
 <p> 가고싶은 도시는? </p>
 <input value={city} onChange={onCity} />
 </div>
 );
}

export default ExampleManyState;
```
event 부분에 target의 value 로 변수를 그대로 (fruit 과 city) 넣어줬으나 에러는 나지 않았다.  
그러나 target 은 input 을 가리키고 그 안의 값인 value 를 가져오기 위해서는 target.value 를 사용해 주는것이 맞다.

여기서 옆그레이드 버젼을 한번 만들어봤다.
- 나이를 올리는 것은 변경하지 않았다. 동일 하다.
- 먹고싶은 과일이 생각 날때 마다 매번 추가할 수 있도록, 그리고 input 안에 값이 button 을 누르면서 초기화 되도록
- 가고싶은 도시가 생각 날때 마다 매번 추가할 수 있도록, 그리고 input 안에 값이 button 을 누르면서 초기화 되도록
  
```JavaScript
import { useState } from 'react';

// component
function ExampleManyState() {
    // state
    const [age, setAge] = useState(60); // 인생은 60부터, 60을 넣어줬다.
    const [fruit, setFruit] = useState(''); // 딸이 포도를 좋아한다. 포도를 넣어줬다. 문자니까 '' 감싸서
    const [fruitList, setFruitList] = useState([]);
    const [city, setCity] = useState(''); // 런던 가보고 싶으니까 런던 을 넣었다. 문자니까 '' 감싸서
    const [cityList, setCityList] = useState([]);
    // event
    const onFruit = (e) => setFruit(e.target.value);
    const onFruitAdd = () => {
        setFruitList((prevState) => [...prevState, fruit]);
        setFruit('');
    };
    const onCity = (e) => setCity(e.target.value);
    const onCityAdd = () => {
        setCityList((prevState) => [...prevState, city]);
        setCity('');
    };

    // JSX
    return (
        <div>
            <p> 살고싶은 나이는 {age} </p>
            <button onClick={() => setAge(age + 1)}>살고싶은만큼 Click</button>
            <hr />

            <p> 먹고싶은 과일은? </p>
            <input value={fruit} onChange={onFruit} />
            <button onClick={onFruitAdd}>과일추가</button>
            {fruitList.map((item, index) => (
                <div key={index}>{item}</div>
            ))}
            <hr />

            <p> 가고싶은 도시는? </p>
            <input value={city} onChange={onCity} />
            <button onClick={onCityAdd}>도시추가</button>
            {cityList.map((item, index) => (
                <div key={index}>{item}</div>
            ))}
        </div>
    );
}

export default ExampleManyState;

```
`해낼거다.`
