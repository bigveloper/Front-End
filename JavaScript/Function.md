# Function
## JavaScript Function(함수) 선언
 - JavaScript 에서 함수를 선언하는 방법은 3가지가 존재한다.
 `1. function statement  (함수 선언문)`
 `2. function expression (함수 표현식)`
 `3. function 생성자`  
 ```JavaScript
  // function statement 함수 선언문
    function a () { console.log('a); };
    
  // function expression 함수 표현식
    const b = function () { console.log(b); };
    const c = () => { console.log('c') };
    
  // function 생성자
    const d = new Function("console.log('d') };
 ```
 function 생성자 함수는 잘 사용되지 않는다.
 
 `() => {};    Arrow Function 이 주로 쓰인다. 이유는 코드를 대폭 줄여주기 때문이다.`
  
  - function statement (함수 선언문) 과 function expression (함수 표현식) 의 차이
    - `JavaScript 에서 함수는 값으로 사용할 수 있다.` 때문에, 익명 함수(anonymous function)를 정의  
      무슨 말이 이렇게 어렵냐?  
      간단하게 말하면 `함수 선언문` 은 함수 호출 시점보다 함수 선언 시점이라고 해도 해당 함수 호출을 당할 수 있단다.  
      그러나 말이 너무 어렵다 어쨋든 함수 호출 할거니까 `함수 표현식` 쓰고 거기서도 코드길이가 적은 `화살표 함수` 쓸란다.  
        
        
  - function expression (함수 표현식) 중에 Arrow Function (화살표 함수) 나 몇번 더 연습 해보자
      
  ```JavaScript
    const arrow()=>{}
  ```
 
 
