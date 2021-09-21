Package.json 

터미널에 
```sh
npm init 
```
입력 후 필요한 정보들을 입력하면 `package.json` 이 만들어진다.
react 같은 경우는
`npm init react-app 폴더명`
을 입력하면 react project 폴더가 생성 된다.

패키지 설치는
`npm install [필요한 패키지 이름]` 명령어로 추가할 수 있다.
`npm i [필요한 패키지 이름]` 곧 약어로 설치도 가능 하다. i = install

일단 package.json 내부를 살펴 보자면,

```
{
    "name": "layout",
    "version": "0.1.0",
    "private": true,
    "dependencies": {
        "@testing-library/jest-dom": "^5.14.1",
        "@testing-library/react": "^11.2.7",
        "@testing-library/user-event": "^12.8.3",
        "react": "^17.0.2",
        "react-dom": "^17.0.2",
        "react-router-dom": "^5.3.0",
        "react-scripts": "4.0.3",
        "web-vitals": "^1.1.2"
    },
    "scripts": {
        "start": "react-scripts start",
        "build": "react-scripts build",
        "test": "react-scripts test",
        "eject": "react-scripts eject"
    },
    "eslintConfig": {
        "extends": [
            "react-app",
            "react-app/jest"
        ]
    },
    "browserslist": {
        "production": [
            ">0.2%",
            "not dead",
            "not op_mini all"
        ],
        "development": [
            "last 1 chrome version",
            "last 1 firefox version",
            "last 1 safari version"
        ]
    }
}

```

여기서 눈여겨 봐야 할 곳은 

```
   "dependencies": {
        "@testing-library/jest-dom": "^5.14.1",
        "@testing-library/react": "^11.2.7",
        "@testing-library/user-event": "^12.8.3",
        "react": "^17.0.2",
        "react-dom": "^17.0.2",
        "react-router-dom": "^5.3.0",
        "react-scripts": "4.0.3",
        "web-vitals": "^1.1.2"
    },
```
`"dependencies" : {}` 이다.
나는 `npm install react-router-dom` 이라는 명령어를 통해 설치를 했고,  
`"dependencies" : {}` 내부에서 설치 된것을 확인 할 수 있다.


패키지를 삭제 하려면 
`npm uninstall react-ruoter-dom`
하면 react-router-dom 은 삭제 된다.
