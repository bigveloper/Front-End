# JSX 란??
- React 에서 생김새를 정의 할 때, 사용하는 문법이다. 얼핏보면 태그(<>)로 이루어진 HTML 같이 생겼지만  
  실제로는 JavaScript 이다.
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
// Failed to compile error
```
그럼 어떻게 해줘야 하느냐
```javascript
`javascript
  return(
    <div className="App">
       <h1> 태그를 닫아줘 </h1>
        <div> 닫아줘 제발</div>
    </div>
  );
}
```
이렇게 하면 된다.
