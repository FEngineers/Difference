# config
```
config(configFn);
```
> Use this method to register work which needs to be performed on module loading.

config阶段是给了ng上下文一个针对constant与provider修改其内部属性的一个阶段

### 什么代码该写到config里面

# run
```
run(initializationFn);
```
> Use this method to register work which should be performed when the injector is done loading all modules.


# ng执行顺序
1. app.config()
1. app.run()
1. directive's compile functions (if they are found in the dom)
1. app.controller()
1. directive's link functions (again, if found)

