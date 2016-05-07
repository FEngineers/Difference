# cookie
setCookie、getCookie都没有现成的，需要自己封装方法

### 删除、修改cookie
cookie并不提供删除、修改的方法，如果想修改某项cookie，只需添加一个同名cookie，新的值将覆盖旧的值。
```
document.cookie = "name=zhangsan";
document.cookie = "name=lisi";  //name被修改为lisi
```

要删除cookie，只需将该cookie有效期设置到当前时间以前即可。
```
var date = new Date();
//设置为前一毫秒（多前都可以）
date.setTime(date.getTime() - 1);
//删除name
document.cookie = "name=lisi;expires=" + date.toGMTString();
```

### 资料
[javascript中的cookie问题](https://segmentfault.com/a/1190000004189877)

[本地存储cookie的封装，提供简单的API](https://segmentfault.com/a/1190000002458465)

[详说 Cookie, LocalStorage 与 SessionStorage](https://segmentfault.com/a/1190000002723469)

[What is the difference between localStorage, sessionStorage, session and cookies?](http://stackoverflow.com/questions/19867599/what-is-the-difference-between-localstorage-sessionstorage-session-and-cookies)