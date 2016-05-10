# JavaScript的运行时(runtime)与解析时(parsetime)

JavaScript代码的执行分成两个步骤，运行时和解析时

### 解析时

在解析时的阶段，解析语法，并且会收集所有的函数声明和变量声明

下面的代码可以正常运行：

```
foo();
function foo() {
  return 5;
}
```

但是下面的代码不能正常执行：

```
foo(); // ReferenceError: foo is not defined
foo = function() {
  return 5;
}
```

下面的代码不能执行：
```
alert(a);
```

下面的代码可以执行：
```
alert(a);
var a;
```

### 运行时
