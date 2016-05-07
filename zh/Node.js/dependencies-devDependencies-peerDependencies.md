# dependencies, devDependencies and peerDependencies, 什么时候该用哪个 ?

### 背景
本文讨论的目的：我们不应该把所有的依赖都丢在dependencies里面。

为什么要存在不同的依赖类型属性，需要知道原因。

### dependencies
依赖的项该是正常运行该项目时所需要的依赖项

整个项目跑起来需要依赖的内容，比如依赖了angular，项目运行时没有angular跑不了，所以要把angular放到dependencies里面

还有，比如loadsh之类的依赖项

### devDependencies
开发的时候需要的依赖项

比如我们写了es6的代码，但是项目运行的时候，我们需要把es6的代码已经转成了es5的，这个时候我们可以把babel放到devDependencies里面

还有一些类似的开发时需要的依赖项：
* 单元测试相关的
* CoffeeScript转成JavaScript相关的
* 压缩代码的
* ...

### peerDependencies
peerDependencies是为插件准备的。


一般情况下，当依赖项还依赖于其它的一些依赖项时，

比如我们上面的dependencies和devDependencies指定了一些依赖项。

但是呢，这些依赖项，竟然又共同的依赖了一些其它的依赖项，而且更糟糕的时，虽然是共同的依赖项，但是版本却是不一样的。

比如说dependency1和dependency2都同时依赖了dependency3，但是依赖的dependency3的版本不一样，看下面的树形结构：
```
root/node_modules/
                 |
                 +- dependency1/node_modules/
                 |                          |
                 |                          +- dependency3 v1.0/
                 |
                 |
                 +- dependency2/node_modules/
                                            |
                                            +- dependency3 v2.0/
```

但是这样发生，尽管package.json里面没有提到过dependency3，虽然有一点奇怪，但是由于存在明细的依赖关系，还是可以正常安装依赖项，结果会如下：
```
root/node_modules/
                 |
                 +- dependency1/
                 |
                 +- dependency2/
                 |
                 +- dependency3 v1.0/
```


不过有的时候在使用插件时，并不会出现明显的依赖关系

假如说，我们想使用grunt的插件grunt-contrib-uglify时以及一些其它的插件，但是插件依赖的grunt的版本是不同的

这个时候，grunt就需要写到peerDependencies里面


### bundledDependencies


### 资料
[What's the difference between dependencies, devDependencies and peerDependencies in npm package.json file?](http://stackoverflow.com/questions/18875674/whats-the-difference-between-dependencies-devdependencies-and-peerdependencies)

[请教一下nodejs package.json的依赖关系定义](https://segmentfault.com/q/1010000000361457)