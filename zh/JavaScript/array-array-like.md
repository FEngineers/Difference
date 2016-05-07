### 类数组
如何判断是否是类数组

### 代码
自己造一个类数组
```
var a = {'0':'a', '1':'b', '2':'c', length:3}; 
```
注意对象的key是从0开始的，看起来好像是数组的下标

类数组可以转变成数组
```
Array.prototype.slice.call(arrLike, 0);
```

那假如
```
var b = Array.prototype.slice.call(a, 0);
b // ["a", "b", "c"]
```

可以如果下标不是从0开始的呢，比如
```
var a = {'1':'a', '2':'b', '3':'c', length:3}; 
var b = Array.prototype.slice.call(a, 0);
var c = Array.prototype.join.call(a, '+');
b // [undefined × 1, "a", "b"]
c // "+a+b"
```

原来类数组的key也是蛮重要的

### 定义
* 拥有length属性，其它属性（索引）为非负整数(对象中的索引会被当做字符串来处理，这里你可以当做是个非负整数串来理解)
* 不具有数组所具有的方法

### 判断类数组
```
var testFunction = function() {
  console.log(Object.prototype.toString.call(arguments)); // [object Arguments] 
};
```

```
var a = {'0':'a', '1':'b', '2':'c', length:3}; 
console.log(Object.prototype.toString.call(a)); // [object Object]
```

不是很好的办法，只能判断出不是数组类型

### 资料
[javascript 类数组](https://segmentfault.com/a/1190000000415572)

[JavaScript 的怪癖 8：“类数组对象”](http://www.html-js.com/article/1619)

[Array-like Objects in JavaScript](https://shifteleven.com/articles/2007/06/28/array-like-objects-in-javascript/)

[Advanced Javascript: Objects, Arrays, and Array-Like objects](view-source:http://www.nfriedly.com/techblog/2009/06/advanced-javascript-objects-arrays-and-array-like-objects/#)




