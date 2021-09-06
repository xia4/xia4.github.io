---
title: "TIL. React Router"
description: "Single Page Application (싱글 페이지 어플리케이션)의 약자이다. 말그대로, 페이지가 1개인 어플리케이션이란 뜻이다.유저가 요청 할 때 마다 페이지가 새로고침 되며, 페이지를 로딩 할 때마다 서버로부터 리소스를 전달받아 해석 후 렌더링을 한다.SPA의"
date: 2021-07-25T04:59:05.048Z
tags: ["React","router"]
---
>## SPA

- Single Page Application (싱글 페이지 어플리케이션)의 약자이다. 말그대로, 페이지가 1개인 어플리케이션이란 뜻이다.
- 유저가 요청 할 때 마다 페이지가 새로고침 되며, 페이지를 로딩 할 때마다 서버로부터 리소스를 전달받아 해석 후 렌더링을 한다.

**SPA의 단점**
1. 앱의 규모가 커지면 Javascript 파일 사이즈가 너무 커진다는 것이다.
2. 자바스크립트를 실행하지 않는 일반 크롤러에서는 페이지의 정보를 제대로 수집해 가지 못한다.
3. 자바스크립트 실행전까지는 페이지가 비어있기 때문에 흰 화면이 나올 수 있다.

( 2, 3번째 단점은 모두 **서버 사이트 렌더링**을 통해 해결이 가능하다.

>## Routing

1. 라우팅이란 다른 경로에 따라 다른 View를 보여주는 것이다.
2. 리액트 자체에는 이러한 기능이 내장되어 있지 않다. 
3. 리액트가 Framework가 아닌 Library로 분류되는 이유
![](/images/157779c7-0255-426e-a0e2-3b92917994c0-image.png)

>## React-router

**1. react-router 설치한다.**

```
npm install react-router-dom --save
```

**2. router 기능 적용**

```
import React from 'react';
import { BrowserRouter as Router, Switch, Route } from 'react-router-dom';
import Login from './pages/Login/login';
import Main from './pages/Main/main';


class Routes extends React.Component {
  render() {
    return (
      <Router>
        <Switch>
          <Route exact path="/login" component={Login} />
          <Route exact path="/main" component={Main} />
        </Switch>
      </Router>
    );
  }
}

export default Routes;

```

**3. route 이동하기**

router.js를 만들었으면 화면을 전환시킬수 있는 두 가지 방법이 있다.

>
<code>Link</code>태그 이용하기
```
import React from 'react';
import { Link } from 'react-router-dom';
class Login extends React.Component {
  render() {
    return (
      <div>
        <Link to="/Main">메인</Link>
      </div>
    )
  }
}
export default Login;
```

<code>a</code> : 새로고침 O, 모든 정보를 새로 다시 받아옴, 외부링크 연결시 사용
<code>Link</code> : 새로고침 X, 필요한 정보만 받아와 보여줌, 내부 페이지 이동시 사용

> <code>this.props.history.push()</code>
```
import React from 'react';
import { withRouter } from 'react-router-dom';

class Login extends React.Component {

  goToMain = () => {
    this.props.history.push('/main');
  }

  render() {
    return (
      <div>
        <button 
            type="submit" 
            className="Btn" 
            onClick={this.goToMain}>
                로그인
        </button>
      </div>
    ) 
  }
}

export default withRouter(Login);
```

<code>this.props.history.push()</code>: 이벤트나 필요 조건에 따라 이동을 하기 위해 사용하는 이동함수
