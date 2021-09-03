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
    return (
    <ToDoTemplate>
      <ToDoInsert onInsert={onInsert} />
      <ToDoList todos={todos} onRemove={onRemove} onToggle={onToggle} />      
    </ToDoTemplate>
  );
}

export default App;
```
App.js 에서 사실 가장 중요한 부분을 꼽으라면 import 되어지는 component 들과 package 라고 해도 절대 과장이 아닐 것이다.<br>
하나하나 알아가보자. 먼저는,<br>
1) useState<br>
 - React 에서는 Hook 이라고 하는 기능이다.<br>
   최상단 import React,{useCallback, useRef, useState} from "react"; 에 useState 가 보여진다. 사용하고 싶을때는<br>
   이렇게 사용하는 것이다.<br>
   function 안에서 변수로 const [todos, setTodos] = useState([내용생략]); 이라고 선언했다. 처음에는 내용이 어려워<br>
   계속 살펴보다 보니, 하나의 변수의 값이 확인하고 업데이트 하는 기능으로 이해가 되었다.<br>
   변수명이 조금 이상하다. [todos, setTodos] 라고 선언 되었다. 이 내용의 뜻은 todos 는 현재의 todos 값, setTodos 는<br>
   todos 의 값을 업데이트 하는 기능을 한다. 결국 현재의 값과, 값을 업데이트를 업데이트 해주는 기능을 가진 메소드 그것이<br>
   useState 이다. 이 내용은 중요하니 따로 더 다루도록 하겠다.<br>
 - 위 내용에 보면 useState([ Object(객체) ]); Array(배열) 안에 Object(객체) 를 두었다. 실행해 보면 사실 보여지는 것은,<br>
   Object 객체의 요소중 text : (todo 내용) 와 checked : (완료여부 토글기능) 만 확인 할 수 있다. 그럼 id 는 뭘까?? <br>
   id 는 ToDoListItem 부분에서 더 알아보기로 하자. 위아래로 왔다갔다 해야 하겠다.<br>
 - 
 
   

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



























<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
https://codecrafting.tistory.com/
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
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
