> 通过这篇，我们也会先学习下JavaScript里的类型

# Class

JavaScript 标准文档中定义: Class 的值只可能是下面字符串中的一个： 
Arguments, Array, Boolean, Date, Error, Function, JSON, Math, Number, Object, RegExp, String.

## Primitive 原始类型
原始类型的值或者数据类型，指的是一个值，这个值既不是object，值上面也没有方法可以使用。
在JavaScript里面，有6种原始类型的的数据类型：
* string
* number
* boolean
* null
* undefined
* symbol

上面有说到原始类型的上面应该没有方法，但是我们却知道string, number也有一些对应的方法。
其实那些是基于原始类型做了封装的对象

### 原始类型的分装对象
除了null, undefined, 其他原始类型都有对象的封装方法：
* String for the string primitive.
* Number for the number primitive.
* Boolean for the Boolean primitive.
* Symbol for the Symbol primitive.

而我们可以通过valueOf这个方法，返回对应的原始值



```
Object.prototype.toString.call(true);
"[object Boolean]"
```


# 参考
https://segmentfault.com/a/1190000000730982


