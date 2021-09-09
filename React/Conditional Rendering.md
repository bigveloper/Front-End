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

