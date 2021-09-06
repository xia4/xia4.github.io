---
title: "TIL.Styled-Components"
description: "styled-component란 Css in JS라는 기술이다.말 그대로 이 기술은 JS안에 Css를 작성하는 것을 의미한다. styled-component는 현존하는 CSS in JS 관련 리액트 라이브러리 중에서 가장 인기 있는 라이브러리이다.사용하기 위해 styl"
date: 2021-08-22T10:39:06.604Z
tags: ["React"]
---
> ## Styled-Components

styled-component란 Css in JS라는 기술이다.
말 그대로 이 기술은 JS안에 Css를 작성하는 것을 의미한다. styled-component는 현존하는 CSS in JS 관련 리액트 라이브러리 중에서 가장 인기 있는 라이브러리이다.

### styled-components 사용하기

사용하기 위해 styled-components를 설치해야한다
```
npm install --save styled-components

yarn add styled-components
```
그리고, 에디터로 해당 프로젝트를 열고 styled라는 이름으로 styled-components 모듈을 import해서 정의해야한다.
```
import styled from "styled-components";
```

### App.js
```
import React from 'react';
import styled from 'styled-components';

const Circle = styled.div`
  width: 5rem;
  height: 5rem;
  background: black;
  border-radius: 50%;
`;

function App() {
  return <Circle />;
}

export default App;
```
npm start 명령어를 사용하여 개발 서버를 실행해보면 다음 화면과 같은 결과가 나타난다.

![](/images/294b6c32-fe68-46eb-a7b5-a44efc84d352-image.png)

styled-component를 사용하면 이렇게 스타일을 입력함과 동시에 해당 스타일을 가진 컴포넌트를 만들 수 있다. 만약에 div를 스타일링 하고싶으면 styled.div, input을 스타일링 하고싶으면 styled.input 이런식으로 사용하면 된다.

이번에는 Circle컴포넌트에 color 라는 props를 넣어보면

### App.js
```
import React from 'react';
import styled from 'styled-components';

const Circle = styled.div`
  width: 5rem;
  height: 5rem;
  background: ${props => props.color || 'black'};
  border-radius: 50%;
`;

function App() {
  return <Circle color="blue" />;
}

export default App;
```
![](/images/7c9fd2b7-9131-430c-a38d-fe9cadad1b07-image.png)

파란색 원이 나타난다.

Circle 컴포넌트에서는 color props값을 설정해줬으면 해당 값을 배경색으로 설정하고, 그렇지 않으면 검정색을 배경색으로 사용하도록 설정되어 있다.