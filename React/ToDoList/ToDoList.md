- # ToDo List
## 1. Todo List 를 만들 때 생각 해야 되는 것
 - ToDo List 에는 `입력`, `검색`,`수정`, `삭제` 의 기능이 다 있다. 곧 우리가 알고 있는 `C R U D` 의 기능이 다 있다.
 - 추가로 할 일을 완료했을 때 check 하는 checkBox 의 기능도 구현 할 수 있다.

## 2. ToDo List 의 기본 기능
 - ToDo Item 입력(추가)
 - ToDo Item 수정
 - ToDo Item 삭제
 - ToDo Item 완료 체크 및 체크 해제
 - ToDo Item 완료 전체 목록 보기

이 부분을 기본적으로 생각하고 작업에 들어간다.  
모든 작업은 React 기본 프로젝트를 구성 할 줄 안다는 가정하에 설명 된다.  

- ## 개발을 시작해 보자

### 1. App.js
```javascript
import React,{useCallback, useRef, useState} from "react";
import ToDoTemplate from "./components/ToDoTemplate";
import ToDoInsert from "./components/ToDoInsert";
import ToDoList from "./components/ToDoList";

function App() {
    const [todos, setTodos] = useState([
      // 객체는 key 와 value로 이루어진다.
      {
          id: 1,
          text: '리액트의 기초 알아보기',
          checked: true,
      },
      {
        id: 2,
        text: '컴포넌트 스타일링 하기',
        checked: true,
      },
      {
        id: 3,
        text: '일정관리 앱 만들어 보기',
        checked: true,
      },
    ]);

    const nextId = useRef(4);

    const onInsert = useCallback(
      (text) => {
          const todo = {
              id: nextId.current,
              text,
              checked: false,
          };
          setTodos(todos.concat(todo));
          nextId.current += 1;
      },
      [todos]
    );
    const onRemove = useCallback(
      (id) => {
        setTodos(todos.filter((todo) => todo.id !== id));
      },
      [todos]
    );

    const onToggle = useCallback(
      (id) => {
        setTodos(todos.map((todo) => (todo.id === id ? {...todo, checked: !todo.checked} : todo)));
      },
      [todos],
    );
    
    return (
    <ToDoTemplate>
      <ToDoInsert onInsert={onInsert} />
      <ToDoList todos={todos} onRemove={onRemove} onToggle={onToggle} />      
    </ToDoTemplate>
  );
}

export default App;
```
 - 추가기능 (onInsert)
   - todos Array(배열) 안에 들어 있는 객체의 Key 로 id , text(내용) , checked(완료여부) , 를 알려 주는 value 가 포함  
     되어 있다. 이 Array(배열) 은 ToDoList 에 porps 로 전달 된다. ToDoList 에서 이 값을 받아오면, ToDoListItem 으로  
     변환하여 rendering 하도록 설정할 것이다.  
   - 등록 버튼을 누르게 되면, onInsert() 함수가 호출된다. 당연히 기존 객체의 key 가 모두 포함 되어 있는 데이터 형태  
     로 호출되어야 한다. id 에는 nextId 값을 넣고 text 에는 전달된 text 값을 그대로 넣는다. 그리고 checked 에는  
     기본값으로 false 를 넣어준다.(=check 가 안되어 있는 상태) 그러면, 이제 만들어진 onInsert() 메소드를  
     항목 추가버튼이 있는 component 인 ToDoInsert 의 props 로 전달한다.
   - useRef 메소드를 이용해 nextId 라는 변수에 4 를 초기화 시키고, 새로 등록된 할 일 객체의 id 로 활용 한다.
 - 삭제기능 (onRemove)
   - React component 에서 Array(배열) 의 불변성 을 지키면서 배열의 원소를 제거 할 때는, 내장 메소드 filter 를 사용하면 좋다.  
     filter 메소드 에는 조건을 확인 해 주는 메소드를 파라미터로 넣어야 한다(조건문 필수). 그래서 반드시 boolean 값을 return 한다.  
     Array(배열) 의 값이 조건문 에서 true 인 경우에만 새로운 Array(배열) 에 포함된다.
   - filter 메소드를 사용하여 onRemove 메소드를 App component 에 작성 하였다. App component 에 id를 파라미터라 받아온 후  
     같은 id 를 가진 항목을 todos Array(배열) 에서 지우는 메소드 이다.  
     (만약에 id : 1 을 지우고 싶다면 이 1 이 미포함 된 Array 를 return 한다. 즉 id : 2 , id : 3 return)
   - useState 를 이용하여 setTodos 를 호출하여 onRemove 메소드를 ToDoList 로 전달 한 후, ToDoListItem component 의  
     props 로 추가한다.  
       
### 2. ToDoInsert
```javascript
import React, {useState, useCallback} from 'react';
import {MdAdd} from 'react-icons/md';
import './ToDoInsert.scss';

const ToDoInsert = ({onInsert}) => {
    const [value, setValue] = useState('');

    const onChange = useCallback((e) => {
        setValue(e.target.value);
    }, []);
    
    const onSubmit = useCallback(
        (e) => {
            onInsert(value);
            setValue('');

            e.preventDefault(); // 브라우저 새로고침/재로드 방지를 위해 사용
        },
        [onInsert, value]
    );
    
    return (
        <form className="ToDoInsert" onSubmit={onSubmit}>
            <input placeholder="할일을 입력하세요." value={value} onChange={onChange} />
            <button type="submit" onSubmit={onSubmit}>
                <MdAdd />
            </button>
        </form>
    );
};

export default ToDoInsert;
```
 - ToDoInsert 는 새로운 할 일을 입력하고 추가할 수 있게 해주는 component 이다.
 - App.js 에서 설명한 내용과 약간중복될 수 있지만, ToDoInsert 에 대한 내용을 살펴보자
 - input 태그 안에서 값을 입력할 때마다, component state 인 value 값에 들어가도록 정의 되었다.
 - ToDoInsert 의 submit 버튼을 눌렀을 때 동작할 메소드 onSubmit 을 만들어 준다. 이 메소드가 호출되면 props 로  
   받아온 onInsert() 메소드의 현재 value 값을 파라미터로 넣어서 호출하고, 현재 value 값을 초기화 한다.  
     
### 3. ToDoListItem
```javascript
import React from 'react';
import { MdCheckBoxOutlineBlank, MdCheckBox, MdRemoveCircleOutline } from 'react-icons/md';
import cn from 'classnames';
import './ToDoListItem.scss';

const ToDoListItem = ({todo, onRemove, onToggle}) => {
    const {id, text, checked} = todo;

    return(
        <div className="ToDoListItem">
            <div className={cn('checkBox', {checked})} onClick={() => onToggle(id)}>
                {checked ? <MdCheckBox /> : <MdCheckBoxOutlineBlank />}
                <div className="text">{text}</div>
            </div>
            <div className="remove" onClick={() => onRemove(id)}>
                <MdRemoveCircleOutline />
            </div>
        </div>
    );
};

export default ToDoListItem;
```
- ToDoListItem 은 각 할일 항목에 대한 정보를 보여주는 component 이다.
- `classnames`를 사용하여 특정 `<div>` 를 제어 할 수 있다. 위에서 checkBox 의 클래스 값을 props 로 넘어오는 `checked` 로  
  결정하고 있다. 이때, checked 의 값이 True 이면 <MdCheckBox /> 를, False 이면 <MdCheckBoxOutlineBlank /> 로 나타낸다.  
  text 역시 마찬가지로 props 로 넘어 오는 데이터 이기 때문에 그대로 {text} 로 출력한다.

### 4. ToDoList
```javascript
import React from 'react';
import ToDoListItem from './ToDoListItem';

const ToDoList = ({todos, onRemove, onToggle}) => {
    return (
        <div className="ToDoList">
            {todos.map((todo)=> (
                <ToDoListItem todo={todo} key={todo.id} onRemove={onRemove} onToggle={onToggle} />
            ))}
        </div>
    );
};

export default ToDoList;
```
- props 로 todos 배열을 받아왔다. 이것을 내장 메소드 map을 통하여 ToDoListItem 으로 이루어진 배열로 변환하여 rendering 했다.
- map 을 이용하여 component 로 변환 할 때는 key props 를 전달 해 주어야 한다. 그리하여 todo 객체의 고유값 중 하나인 id를 전달해 주었다.  
  그리고 ToDoListItem 에서 다룰 데이터를 통으로 props 를 전달한다.  
    
    
  - Javascript 배열의 map() 메소드는 반복되는 component 를 rendering 할 때 `필수적` 으로 사용되는 메소드 이다.
  - map() 메소드는 파라미터 로 전달된 메소드를 사용하여 Array(배열) 안의 각 요소를, 원하는 규칙에 따라 변환한 후 그 결과로 새로운  
    Array(배열)을 생성한다.  

  
- 추후에 지속적으로 업데이트 하겠지만, ToDoList 를 하면서 잡은 React 혹은 SAP 개념 으로는,  
  1. component 들로 이루어져 있다.
  2. 각 component 는 각자의 할일이 주어져 있다.
  3. component 가 주어진 일을 하기 위해선, 데이터가 필요한데 그것이 `props` 이다. 즉, `props`의 값으로  
     component 들이 유기적으로 작업한다.(각 component 들은 당연히 import 해야 한다.)
  4. `prop` 이 useState 를 거치면서 입력, 수정, 삭제, 토글(checked) 의 기능까지 업데이트 한다. 

























<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
- 참조<br>
https://codecrafting.tistory.com/<br>
https://gist.github.com/ninanung<br>
https://react.vlpt.us/<br>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
1) useState  
 - React 에서는 Hook 이라고 하는 기능이다.  
   최상단 import React,{useCallback, useRef, useState} from "react"; 에 useState 가 보여진다. 사용하고 싶을때는  
   이렇게 사용하는 것이다.  
   function 안에서 변수로 `const [todos, setTodos] = useState([내용생략]);` 이라고 선언했다. 처음에는 내용이 어려워  
   계속 살펴보다 보니, 하나의 변수로 값을 확인하고 업데이트 하는 기능으로 이해가 되었다.  
   변수명이 조금 이상하다. `[todos, setTodos]` 라고 선언 되었다. 이 내용의 뜻은 todos 는 현재의 todos 값, setTodos 는  
   todos 의 값을 업데이트 하는 기능을 한다. 결국 현재의 값과, 값을 업데이트를 해주는 기능을 가진 메소드 그것이  
   useState 이다. 이 내용은 중요하니 따로 더 다루도록 하겠다.  
 - 위 내용에 보면 `useState([ Object(객체) ]);` Array(배열) 안에 Object(객체) 를 두었다. 실행해 보면 사실 보여지는 것은,  
   Object 객체의 요소중 text : (todo 내용) 와 checked : (완료여부 토글기능) 만 확인 할 수 있다. 그럼 id 는 뭘까??  
   id 는 ToDoListItem 부분에서 더 알아보기로 하자. 위아래로 왔다갔다 해야 하겠다.  
 - useState 의 요소로 Array(배열)을 사용 하지 않을 수도 있지만, ToDoList 기능에는 할일과 할일을 완료했을 때 체크 해주는 기능도  
   함께 있어야 하다 보니 Object(객체) 로 만들어 Array(배열)의 요소로 만든 것이다.  
     
     
   
 - useState 의 값들로 id 값으로 보자면 3 번 까지 이미 들어가 있고 그 밑에 다른 nextId = useRef(4); 라고 선언 되었다.  
   이미 id 값이 3 번까지 들어가 있기 때문에 다음에 들어오는 id 값은 4 번 으로 시작하겠다는 뜻이다. 일단은 여기까지만 알자.  
     
     
2) useCallback
 - useCallback 은 특정 메소드를 새로 만들지 않고 재사용하고 싶을때 사용하게 됩니다.
 - 이 코드에서 설명하자면 ToDoInsert component 도 이해하고 있어야 하니 내용을 살펴보면 좋겠다.
 - 여기서 useCallback 의 값으로 text 가 들어오게 된다. 그 내용은 ToDoInsert 의 return 부분부터 살펴보자면  
   <input /> 내부에 할 일에 대한 내용을 입력하여 onChange Event 가 발생하게 되면 todo 라는 객체 안의 요소처럼  
   id, text, checked 으로 todos 안에 `concat` 곧 합쳐지게 되는 것이다. 결국 객체가 합쳐지는 것이지만 요소가  
   위 3가지로 되어 있다는 것을 기억하고 그리고 나서는 nextId 변수 안의 값은 1을 올리게 된다.  
   ToDoInsert 에서 좀 더 설명하도록 하겠다.  
     
     
이 내용은 추후에 공부하기로 하자
- # ToDo List
## 1. Todo List 를 만들 때 생각 해야 되는 것
 - ToDo List 에는 `입력`, `검색`,`수정`, `삭제` 의 기능이 다 있다. 곧 우리가 알고 있는 `C R U D` 의 기능이 다 있다.
 - 추가로 할 일을 완료했을 때 check 하는 checkBox 의 기능도 구현 할 수 있다.

## 2. ToDo List 의 기본 기능
 - ToDo Item 입력(추가)
 - ToDo Item 수정
 - ToDo Item 삭제
 - ToDo Item 완료 체크 및 체크 해제
 - ToDo Item 완료 전체 목록 보기

이 부분을 기본적으로 생각하고 작업에 들어간다.<br>
모든 작업은 React 기본 프로젝트를 구성 할 줄 안다는 가정하에 설명 된다.<br>

## 3. 화면 구성 기획
 - 맨 위에 ToDo Item 을 입력(추가) 할 수 있는 창과 버튼을 만든다.
 - 아래 에는 ToDo Item 목록이 존재한다. 목록은 두개의 그룹으로 나눌 것이다.
   - 첫번째 그룹은 ToDo Item 곧 '할 일' 에 대한 목록
   - 두번째 그룹은 완료한 ToDo Item 곧 '완료한 일' 에 대한 목록 곧 '완료한 목록'
 - '할 일' 목록은 편집과 삭제가 가능 하다.
 - '완료한 일' 목록은 삭제만 가능하다.
 - ToDo List 앞에는 checkBox 가 있다. check 하면 '완료한 일' 이 됨으로 '완료한 목록'으로 이동
 - checkBox 에서 check 를 해제하면 '할 일' 목록으로 이동 시킨다.

## 4. 전체적인 틀 개발
- ### 전체적인 틀 개발
- 디렉토리(폴더) 구조
  - 디록토리(폴더) components 와 pages 를 scr 내부에 생성 한다.
  - components 는 화면을 구성하는 기능적인 부분에 있어 component 를 단위로 jsx 파일로 생성 하였다.
  - pages 는 화면 단위로 jsx 파일로 생성 하였다.
  <br><br>
     - 이번 프로젝트 에서는 하나의 페이지만 있어도 되지만, 추후에 여러 페이지를 생성 할 가능성 으로 따로<br>
      pages 디렉토리(폴더)를 만들었다.
  <br>
 - pages
   - Home : 첫 화면(ToDo List 를 보여 준다.)
 - components
   - ToDo Item 을 입력 받을 수 있는 component
   - ToDo Item 의 List compnent (ToDo Item conponent 들을 포함)
   - ToDo Item compotnent

## 5. 개발을 시작해보자
 ### 1) jsx 파일들을 생성한다.
 - 생성한 compnents 폴더 안에 jsx 파일 생성
    - inputBox.jsx
    - ToDoItem.jsx
    - ToDoItem.jsx
 - 생성한 pages 폴더 안에 jsx 파일 생성
    - Home.jsx
 
 ### 2) App.js
 page 를 rendering 한다. 지금 프로젝트 에서는 하나의 페이지만 필요하여 Home.jsx 만 rendering 한다.<br>
 (추후 혹은 다른 프로젝트에서 기능을 고도화 시키면 라우팅 이라는 기능을 넣을 수 있다.) -> 이건 더 공부해야 함






<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
- 참고<br>
https://memostack.tistory.com/
