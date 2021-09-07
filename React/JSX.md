# JSX 란??
- ## React 에서 생김새를 정의 할 때, 사용하는 문법이다. 얼핏보면 `태그(<>)로 이루어진` HTML 같이 생겼지만  
  실제로는 `JavaScript` 이다.
```javascript
  return(
    <div className="App">
      <div>안녕하세요</div>
    </div>
  );
}

export default App;
```
- 태그`<>,</>` 또는 `<내용 />` 으로 꼭 닫혀 있어야 함 다시말해서,
```javascript
  return(
    <div className="App">
       <h1> 태그를 닫아줘
        <div> 닫아줘 제발
        
  );
}

export default App;
// Failed to compile error
```
그럼 어떻게 해줘야 하느냐
```javascript
  return(
    <div className="App">
       <h1> 태그를 닫았군 </h1>
        <div> 정말 고마워 </div>
    </div>
  );
}

export default App;
```
이렇게 하면 된다.

- ## JSX 에 표현식 포함하기
- JSX 의 `중괄호 {}`  안에서는 `유효한 모든 JavaScript 표현식`을 넣을 수 있다.
```javascript
import "./App.css";

function App() {
    const name = "whyj";
    const elements = <h1>Hello, {name} !!!</h1>;

    return <div>{elements}</div>;
}

export default App;

// Hello, whyj !!!
```
  - JSX 도 표현식 이다.
       - 컴파일이 끝나면, JSX 표현식이 정규 JavaScript 함수 호출이 되고 JavaScript 객체로 인식 된다.
       - 즉, JSX 를 if 구문 및 for loop 안에 사용하고, 변수에 할당하고, 인자로서 받아들이고 함수로 부터 반환 할 수 있다.
       - 아래에서 간단하게 살펴본다. 다만 React JSX 에서는 if 보다는 `삼항연산자` 를 for 보다는 `map()` 를 사용한다.
```javascript
import "./App.css";

function App() {
    const name = "whyj";

    return 
    name === "whyj" ? <div>잘생겼다.</div> : <div>못생겼다.</div>;
}

export default App;

// 잘생겼다.
```
whyj 가 아닐때를 살펴보자
```javascript
import "./App.css";

function App() {
    const name = "whyj";

    return 
    name === "나는" ? <div>잘생겼다.</div> : <div>못생겼다.</div>;
}

export default App;

// 못생겼다.
```
React JSX 에서의 if 에 대해서는 중요한 내용이다 보니 따로 설명한다.  
