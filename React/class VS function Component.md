# class Component
- 기본적으로 class Component 와 function Component 가 하는 동작은 같다.  
  그러나, class Component 가 function Component 가 더 많은 기능을 제공 해 주었다.  
  그래서, 많이 사용 했지만 이제는 사실 사용하지 않는다. 기본형만 알아보자
  
```JavaScript
import React, { Component } from 'react';
class ClassComp extends React.Component {
  state = {
    // ...
  };
  render() {
    return (
      <div className="container">
        //...
      </div>
    )
  }
}
```
state 를 정의하고, render 함수의 return 값에 따라 원하는 화면을 보여 준다.  
  
사실 이제 React 버전 16.8 에 새로 추가된 Hook 으로 인해 상황은 달라 졌다.  
`Hook` 은 따로 설명 해 두었다. 
  
# function Component
- React 버전 16.8 이 나오기 전까지는 비교적 간단한 동작을 하는데 사용 되었다.  
  `state` 와 `lifecyle`에 정의된 함수를 사용하지 못했기 때문이다. 기본형을 알아보자  
    
```JavaScript
function FuncComp(props) {
  return (
    <div classNmae="container">
    // ...
    </div>
  );
}
```
간단해 보인다. 그러나 Hook 을 이용해 function Component 에서도 class 처럼 여러가지 동작이 가능하다.  
  
## function Component 에 state 생성하기
 - function Component 에서 생성하는 방법은 `useState` 라는 메소드를 사용한다. 중요하다!!  
```JavaScript
import { useState } from 'react'; // 가져다 써야지 안가지고 왔는데 어떻게 쓰나

const [value, setValue] = useState(value);
// useState(''); 로도 사용이 가능하다.
```

state 는 값을 저장하거나 변경할 수 있는 객체로 보통 `event`와 함께 사용된다.  
  
## useEffect 사용하기
 - function Component 에서 lifecyle 메소드를 사용하기 위해서는 `useEffect` 라는 메소드를 사용해야 한다.  
   `useEffect`의 effect 는 side effect 곧, 동작 후 일어나는 부수적인 효과 다.
 - `useEffect`는 여러개를 사용할 수 있고, `return`을 사용하여 `cleanup`동작을 수행 할 수 있다.
 - 두번째 인자로(첫번째 인자는 function) 배열을 줘서 그 배열에 있는 변수들의 값이 바뀔 때만 useEffect 가  
   동작하게 하는 skipping effect 동작을 수행 할 수 있다. 이 부분은 따로 알아본다.
   
## 결론
 - 현재는 class Component 보다는, function Component 를 많이 사용한다. 
 - 이전에는 제약 사항들이 존재했으나 React 버전 16.8 이후로 Hook 이란 존재가 나타났기 때문이다.
 - 그럼 Hook 에 대해서 더 많이 알아 두면 좋겠다.
