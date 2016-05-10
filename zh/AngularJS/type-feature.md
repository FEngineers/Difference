比较ng项目的目录结构

主要目的：怎么组织angular的代码结构，才是最佳的，好理解、好维护

除了简单的介绍目录结构，也结合es2015和webpack来看看组织代码结构

主要有两种：
* Sort By Type
* Sort By Feature

### Sort By Type
Sort By Type适合小项目

### Sort By Feature
Sort By Feature适合组织大项目

### es6 ng
怎么样能够在angular的项目里充分地使用es6的新特性

一般的项目结构会组织如下

```
client
⋅⋅app/
⋅⋅⋅⋅app.js * app entry file
⋅⋅⋅⋅app.html * app template
⋅⋅⋅⋅common/ * functionality pertinent to several components propagate into this directory
⋅⋅⋅⋅components/ * where components live
⋅⋅⋅⋅⋅⋅components.js * components entry file
⋅⋅⋅⋅⋅⋅home/ * home component
⋅⋅⋅⋅⋅⋅⋅⋅home.js * home entry file (routes, configurations, and declarations occur here)
⋅⋅⋅⋅⋅⋅⋅⋅home.component.js * home "directive"
⋅⋅⋅⋅⋅⋅⋅⋅home.controller.js * home controller
⋅⋅⋅⋅⋅⋅⋅⋅home.styl * home styles
⋅⋅⋅⋅⋅⋅⋅⋅home.html * home template
⋅⋅⋅⋅⋅⋅⋅⋅home.spec.js * home specs (for entry, component, and controller)
```

从上面的结构，很重要的一个点就是 entry文件

entry文件需要很清晰的标明app结构，component结构

[NG6-starter](https://angularclass.github.io/NG6-starter/)

https://github.com/AngularClass/NG6-todomvc-starter
http://panthersoftware.com/2015/09/08/yet-another-angular-es6-webpack-seed/

### angular webpack
webpack一般会需要指明一个entry文件，那如果之前的build的方法是通过指定文件夹，
那么我们可能需要在一个js里面，require或者import我们依赖的文件，这样对代码的组织最好能合理一点，
在需要import、require的地方再去import、require

https://github.com/preboot/angular-webpack
https://segmentfault.com/a/1190000002490637)
https://segmentfault.com/a/1190000003915443
http://angular-tips.com/blog/2015/06/using-angular-1-dot-x-with-es6-and-webpack/

### 参考：
http://stackoverflow.com/questions/18542353/angularjs-folder-structure

http://www.johnpapa.net/structuring-an-angular-project/

https://github.com/toddmotto/angular-styleguide

https://scotch.io/tutorials/angularjs-best-practices-directory-structure

http://angularjs.blogspot.com/2014/02/an-angularjs-style-guide-and-best.html

https://google.github.io/styleguide/angularjs-google-style.html

https://docs.google.com/document/d/1XXMvReO8-Awi1EZXAXS4PzDzdNvV6pGcuaF4Q9821Es/pub

