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

