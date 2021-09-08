# React Event
## React element(요소) 의 event 를 제어하는 것은 DOM element event 를 제어하는 것과 매우 유사하다. 그러나, 몇가지 문법적인 차이가 있다.
 - React event 는 소문자 대신 `camelCase` 를 사용한다.
 - JSX 에 `문자열` 대신 `함수` 를 전달한다.

예를 들어 HTML 에서 event 를 넣을때,
```HTML
<button onclick="super()"> super </button>
```
이라면, React 에서는 조금 다르다.
```JavaScript
<button onClick={super}> super </button>
```
`camelCase` 를 사용한 것을 볼 수 있다.

