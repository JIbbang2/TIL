## React 기초

> 벨로퍼트와 함께하는 모던 리액트 참고



#### 1. 새 프로젝트 만들기

```javascript
$ npx create-react-app begin-react(디렉토리 명)
$ cd begin-react
$ npm start or yarn start (서버 켜기) 
```



**❓ npm과 yarn**

> 자바스크립트 런타임 환경인 Node.js의 패키지 관리자

- **npm**(Node Package Manager) : 노드를 설치할 때 자동으로 설치되는 기본 패키지 관리자

- **yarn** : 페이스북에서 React와 같은 프로젝트를 진행하며 겪었던 어려움을 해결하기 위해 페이스북에서 개발한 패키지 관리자. npm보다 속도나 안정성 측면에서 향상됨

- 차이점
  1. 속도 : npm은 패키지를 한번에 하나씩 순차적으로 설치, yarn은 여러 패키지를 동시에 가져오고 설치(병렬 설치). yarn이 패키지 설치 속도 측면에서 빠름
  2. 보안 : yarn이 더 안전함. npm은 자동으로 패키지에 포함된 다른 패키지 코드를 실행함. yarn은 yarn.lock 또는 package.json 파일에 있는 파일만을 설치함.



#### 2. Component 생성

- Hello.js라는 컴포넌트 생성하기

```javascript
// src/Hello.js

// 리액트 불러와주기
import React from 'react';

// 함수형태 or 클래스 형태로 작성 가능
function Hello() {
  return <div>안녕하세요</div>
}

// Hello라는 컴포넌트를 내보내겠다. 다른 컴포넌트에서 불러와서 사용 가능
export default Hello; 
```

- Hello.js를 App.js에서 불러와서 사용하기

```javascript
// src/App.js

import React from 'react'
// Hello.js 불러오기
import Hello from './Hello'

function App() {
  return (
    <div>
      {/* App.js 내부에 Hello.js 컴포넌트를 불러와서 보여줌 */}
      <Hello /> 
    </div>
  )
} 

export default App
```



#### 3. JSX

- JSX란 JavaScript를 확장한 문법으로, UI가 어떻게 생겨야 하는지 설명하기 위해 React와 함께 사용할 것을 권장함

- input 또는 br태그 등을 사용할 때도 태그를 닫아야함

  ```javascript
  <input /> 
  <br />
  ```

- function의 return 내부는 하나의 태그로 감싸기

  - Fragment 
    - div 태그로 내용을 감싸기 애매할 때 사용함
    - 이름 없는 태그로, 작성 시에도 브라우저 상에서 따로 별도의 엘리먼트로 나타나지 않는다.

  ```javascript
  import React from 'react';
  import Hello from './Hello';
  
  function App() {
    return (
      <>
        <Hello />
        <div>안녕히계세요</div>
      </>
    );
  }
  
  export default App;
  ```

- 변수를 나타낼때는 '{}' 사용

  ```javascript
  import React from 'react';
  import Hello from './Hello';
  
  function App() {
    const name = 'react';
    return (
      <>
        <Hello />
        <div>{name}</div>
      </>
    );
  }
  
  export default App;
  ```

- style 작성하기
  - 인라인 스타일은 객체형태로 작성하기
  - -로 구분되어 있는 이름은 camelCase로 작성하기
- css class 설정하기
  - className 으로 설정하기

- JSX 내부의 주석
  - {/* comment */} 의 형태로 작성함. 중괄호로 감싸지 않으면 화면에 보인다.



#### 4. props를 통해 컴포넌트에게 값 전달하기 

> props란 properties의 줄임말로 어떠한 값을 컴포넌트에 전달해주어야 할 때 사용함

- 값 전달하기

  ```javascript
  // App.js / name이란 값 전달하기
  import React from 'react';
  import Hello from './Hello';
  
  function App() {
    return (
      <Hello name="react" />
    );
  }
  
  export default App;
  ```

- 값 전달 받아 사용하기

  ```javascript
  // Hello.js
  import React from 'react';
  
  function Hello(props) {
    return <div>안녕하세요 {props.name}</div> 
  }
  
  export default Hello;
  ```

  
