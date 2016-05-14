# ng执行顺序
1. app.config()
1. app.run()
1. directive's compile functions (if they are found in the dom)
1. app.controller()
1. directive's link functions (again, if found)





http://hellobug.github.io/blog/angularjs-directive-2-compile-vs-link/
