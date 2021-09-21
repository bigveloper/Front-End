React
- 함수의 정의 처럼 단방향 사고를 강제 함
- 특정 state, props 에 따른 render 결과가 바뀌지 않음
- JSX 를 통해 어떻게 화면에 그릴지 정의 함
- 함수 간 함성이 가능하듯이, 컴포넌트 간 합성이 가능하다.
  
    
    Component
    - component 는 독립적이고 재사용이 가능하다.
    - JavaScript 함수와 동일하게 작용하지만, 독립적으로 작동하고 render() 함수를 통해 HTML 을 반환한다.
    
    1. React 컴포넌트를 생성할 때 컴포넌트의 이름은 대문자로 시작해야 한다.
    2. 컴포넌트의 구성요소는 다음과 같다.
    ```
    function Car() {
      return <h2>Hi, I am also a Car!</h2>;
    }
    export default Car;
    ```
    3. export 는 다른 파일에서 Car 파일을 import 하도록 정의 해 주는 것이다.
        - default 는 하나의 component 만 export 하는 것
        - import 할 때도 Car 하나만 import 할 수 있다.
    
