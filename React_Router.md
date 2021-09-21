Router
 - 다른 주소의 다른 화면을 보여준다.
 - 리액트가 공식적으로 지원하는 라우터(router) 기능이 없다. 라이브러리를 따로 설치 해줘야 한다.
 `npm install react-router-dom`
 - index.js 에 들어가보면
 ```
 import './index.css';

import React from 'react';
import ReactDOM from 'react-dom';
import { BrowserRouter } from 'react-router-dom';

import App from './App';
import reportWebVitals from './reportWebVitals';

ReactDOM.render(
    <React.StrictMode>
        <BrowserRouter>
            <App />
        </BrowserRouter>
    </React.StrictMode>,
    document.getElementById('root')
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();

 ```
 `import { BrowserRouter } from 'react-router-dom';` 라고 import 받아서
 <App /> 을 감싸준다.
 ```
         <BrowserRouter>
            <App />
        </BrowserRouter>
 ```
 
 여기 보여지는 내용들을 잘 기억하자.
 <App /> 에서 <BrowserRouter> 를 사용하기 위해서 감싸줬다.
 
 그리고 실제로 router 가 사용되는 component 를 만들어 준다.
 ```
 import { Route, Switch } from 'react-router-dom';

import Menu01 from '../pages/Menu01';
import Menu02 from '../pages/Menu02';
import Menu03 from '../pages/Menu03';
import Menu04 from '../pages/Menu04';
import Menu05 from '../pages/Menu05';

/**
 * @description Router
 */
function Router() {
    return (
        <Switch>
            <Route path="/menu01" component={Menu01} />
            <Route path="/menu02" component={Menu02} />
            <Route path="/menu03" component={Menu03} />
            <Route path="/menu04" component={Menu04} />
            <Route path="/menu05" component={Menu05} />
        </Switch>
    );
}

export default Router;

 ```
 path 로 경로를 지정해 주고, 보여줄 component 도 지정해 준다.
  
router 를 정의 하자면, 먼저 SPA 의 개념을 이해하고 다른 주소의 다른 페이지를 새로고침 없이 화면에서 보여주는 기능 이다.
 
 
