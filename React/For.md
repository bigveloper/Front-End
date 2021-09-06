# React 에서 For 문 사용하기
```JavaScript
import React from 'react';

function App() {
    const weekArr = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'];

    return (
      <div>
        {
          for(let i = 0; i<weekArr.length; i++)
            {
              <span>{weekArr(i)</span>
            }
        }
      </div>
    );
}

export default App;

```
일반적인 JSX 문법으로 return 안에서는 for 문을 사용할 수 없다.
```JavaScript
import React from 'react';

function App() {
    const weekArr = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'];

    const rendering = () => {
        const reuslt = [];
        for (let i = 0; i < weekArr.length; i++) {
            reuslt.push(<span key={i}>{weekArr[i] + ' / '}</span>);
        }
        return reuslt;
    };
    return <div>{rendering()}</div>;
}

export default App;
```
먼저 배열변수(weekArr)를 선언하여 요소 들을 넣고, 그 후에 다시 메소드(rendering)를 선언한다.  
함수 안에 빈배열(result) 변수를 선언하고 for 문을 이용하여 먼저 선언된 배열변수 안의 값을 순회하면서  
빈배열에 배열 메소드인 push 를 통해 밀어 넣어준다. 이 때, 배열의 값을 확인 하기 위해서는 Key 값은 필수다.  
그때 for 문에서 선언 해준 `i` 를 `Key` 값으로 가져왔다. 그리고 result 를 반환 해주었다.

결국 최종적으로 return 내부 JSX 에서 함수를 호출함으로 값을 화면에 보여준다.

반환된 값으로는  
`Mon / Tue / Wed / Thu / Fri / Sat / Sun /`
가 잘 나왔다.
