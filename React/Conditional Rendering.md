# React 에서 if 문을 사용해 보자
- component 안에서 사용해 보기
```JavaScript
import "./App.css";

function App() {
    if (true) {
        return <h6> true 면 잘생겼다.</h6>;
    } else {
        return <h6>아니면 못생겼다.</h6>;
    }
}

export default App;

/// true 면 잘생겼다. 
/// 여기서 false 혹은 0 을 넣어주면 else 가 실행된다.
```
사실 if 문은 JSX 안에서 사용이 불가하다. 그리하여 사용하는 것이 `삼항 연산자` 이다. (전혀 사용 못하는 것은 아님..)

# React JSX 에서 `삼항 연산자` 사용하기(=조건문)

```JavaScript
import "./App.css";

function App() {
    const name = "whyj";

    return (
        <div>{name === "whyj" ? <p> 잘생겼다. </p> : <p> 못생겼다. </p>}</div>
    );
}

export default App;

// 잘생겼다.
```
# React && 연산자로 if 문 처럼 표현하기
JSX 안에서는 중괄호를 이용해서 표현식을 포함 할 수 있습니다. 그 안에 JavaScript 의 논리 연산자 && 를 사용하면  
쉽게 엘리먼트를 조건부로 넣을 수 있다.

설명이 class 컴포넌트로 되어 있는 것들이 많아, 먼저 class 컴포넌트와 function 컴포넌트의 차이를 확인하고 다시 차근히 신속히 알아보겠다.
