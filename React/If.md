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
