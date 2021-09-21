<h1>URL</h1>
- url 은 인터넷에서 자원 위치 를 나타낸다.
- url 은 웹에서 정해진 유일한 자원의 `주소` 일 뿐이다.
- 이론적으로는 각각의 유일한 url은 유일한 자원을 가리킨다. -> HTML 페이지, CSS 문서, 이미지 등이 될 수 있다.
  
  - 기본 URL 의 구조
  `http://www.example.com:80/path/to/myfile.html?key1=value1&key2=value2#SomewhereInTheDocument`  
 - `http`: protocol  
  `http` 는 프로토콜(규약)이다. url 의 첫 파트는 브라우저가 어떤 규약을 사용해야 하는 지를 나타낸다. 프로토콜은 컴퓨터의 네트워크에서  
  데이터를 교환하거나 전송하기 위한 방법들의 세트이다. 보통 웹사이트들을 위해, 이것은 HTTP 프로토콜이나 HTTP 프로토콜의 보안 버전입니다.  
  웹은 두가지 중 하나를 요구한다. 그러나 브라우저는 `mailto:`(메일 클라이언트를 열기 위한), 또는 파을을 전송하기 위한 `ftp:` 와 같은  
  프로토콜 들을 다루는 방법이 있다.  
 -  `www.example.com` : domain name  
  `www.example.com` 은 도메인 이름이다. 이것은 어떤 웹서버가 요고뒤는 것인 지를 가리킨다. 대안으로 직접 IP adderss 를 사용하는 것도  
  가능하다. 그러나 덜 편리하므로 웹에서는 주로 사용되지는 않는다.  
 -  `:80` : port  
  `:80` : 는 포트 이다. 이것은 기술적으로 웹서버에서 자원에 접근하기 위해 사용하는 gate 관문을 가리킨다. 만약 웹서버가 자원의 접근을 하기 위해  
  표준 http 포트, http 80, https 443 을 사용한다면 포트 번호는 생략하지만, 그렇지 않으면 포트 번호는 필수 이다.  
 - `/path/to/myfile.html` : path to the file  
  `/path/to/myfile.html` 는 웹서버에서 자원에 대한 경로이다. 초기의 웹에서는, 웹서버상에서 물리적인 파일의 위치를 나타냈으나 요즘에는 실제  
  물리적 경로를 나타내지 않고, 웹 서버에서 추상화 하여 보여준다.  
 - `?key1=value1&key2=value2` : parameters  
  `?key1=value1&key2=value2` 는 웹서버에서 제공하는 추가 파라미터 이다. 이 파라미터들은 & 기호로 구분된 key/value짝을 이룬 리스트 이다.  
  이전 웹 서버는 자원을 반환하기 전에 추가적인 작업을 위해 이런 파라미터들을 사용했다. 각각의 웹서버는 파라미터들을 언급하는 자신의 규칙을 갖고 있다.   
  그리고 특정한 웹서버가 파라미터를 다루는 지 알기 위한 유일한 방법은 웹서버 소유자에게 질문해야 한다.  
 - `#SomewhereintheDocument` : Anchor  
  `#SomewhereintheDocument` 는 자원 자체의 다른 부분에 대한 anchor(닻) 이다. An anchor는 일종의 자원 안에서 "bookmark" 이다. 즉,  
  "bookmarked" 지점에 위치된 내용을 보여주기 위해 브라우저에게 방향을 알려 준다. 예를 들어 HTML 문서에서 브라우저는 anchor 가 정의한 곳의 점을  
  스크롤 하는데, 비디오나 오디오 문서에서, 브라우저는 앵커가 나타나는 시간을 찾으려 할 것이다. # 뒤에 오는 부분은 별 의미가 없다. 또한  
  fragment identifier(부분 식별자) 라고 알려져, 요청이 서버에 절대 보내지지 않는다.  
  
  <h1>절대URL 와 상대URL</h1>
  - 전체 url(이전에 사용한 것 과 같다)
  `http://developer.mozilla.org/en-US/docs/Learn`
  - 내포된 프로토콜
  `//developer.mizilla.org/en-US/docs/Learn`
  - 내포된 도메인명
  `/en-US/docs/Learn
  - 이것은 HTML 문서 내에서 절대 URL 을 위한 가장 흔한 방법이다.
