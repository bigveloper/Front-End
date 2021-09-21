<h1>JSDoc</h1>
JSDoc이란 JavaScript 소스 코드에 대한 설명을 하기 위해 사용되는 마크업 언어임  
HTML의 경우 태그는 꺽쇠 기호(<>)를 사용하여 태그를 표현하지만 JSDoc의 경우 @을 사용하여 태그를 표현함  
JSDoc에서 지원하는 태그는 block tag와 inline tag로 나눠지는데요. 사용 문법이 약간 다름  
  
@alias(block tag)와 @link(inline tag) 태그로 차이점을 확인해보면:  
Block tag  
```
/**
* Bar function.
* @alias bar
*/
function foo() {}
```
  
Inline tag  
```
/**
* See {@link MyClass} and [MyClass’s foo property]{@link MyClass#foo}.
* Also, check out {@link http://www.google.com|Google} and
* {@link https://github.com GitHub}.
*/
function myFunction() {}
```  
HTML의 block tag, inline tag와 비슷하게 주석 안에서 한 줄을 차지하느냐(block tag) 주석 안의 다른 설명 안에 속하느냐(inline tag)에 따라 다른 것을 확인할 수 있습니다.  
대부분의 태그들의 경우 block tag 이며 inline tag는 @link 와 @tutorial 뿐입니다.  

- <참고>  
https://jsdoc.app/index.html  
  
  https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html  

  
    
