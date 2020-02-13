# react-router

1. install

```js
npm install --save react-router-dom
```

2. demo

```js
import React from "react";
import { BrowserRouter as Router, Route, Link } from "react-router-dom";

function Index() {
  return <h2>JSPang.com</h2>;
}

function List() {
  return <h2>List-Page</h2>;
}

function AppRouter() {
  return (
    <Router>
      <ul>
        <li>
          {" "}
          <Link to="/">首页</Link>{" "}
        </li>
        <li>
          <Link to="/list/">列表</Link>{" "}
        </li>
      </ul>
      <Route path="/" exact component={Index} />
      <Route path="/list/" component={List} />
    </Router>
  );
}
export default AppRouter;
```

### react-router 动态传值

- patch:自己定义的路由规则，可以清楚的看到是可以产地 id 参数的。
- url: 真实的访问路径，这上面可以清楚的看到传递过来的参数是什么。
- params：传递过来的参数，key 和 value 值。

### React Router Redirect

1. 标签式重定向

```js
import { Link, Redirect } from "react-router-dom";
<Redirect to="/home/" />;
```

2. 编程式重定向

### 嵌套路由

```js
import React from "react";
import { Route, Link } from "react-router-dom";
import Reactpage from "./video/ReactPage";
import Vue from "./video/Vue";
import Flutter from "./video/Flutter";

function Video() {
  return (
    <div>
      <div className="topNav">
        <ul>
          <li>
            <Link to="/video/reactpage">React教程</Link>
          </li>
          <li>
            <Link to="/video/vue">Vue教程</Link>
          </li>
          <li>
            <Link to="/video/flutter">Flutter教程</Link>
          </li>
        </ul>
      </div>
      <div className="videoContent">
        <div>
          <h3>视频教程</h3>
        </div>
        <Route path="/video/reactpage/" component={Reactpage} />
        <Route path="/video/vue/" component={Vue} />
        <Route path="/video/flutter/" component={Flutter} />
      </div>
    </div>
  );
}
export default Video;
```

### 后台动态获取路由配置
