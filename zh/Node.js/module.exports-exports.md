事情是这样的，有一段代码是用es6写的

// foo.js
export default function() {
  console.log('hi);
}

被调用的地方，并没有使用es6的import，使用的是
```
require('./foo.js);
```

原因是什么？

项目里有使用到webpack和babel

这种支持是webpack做的还是babel做的


小伙伴查了下发现了如下的内容

```
// 在 ES2015 中，模块通过export语句来输出
// 普通输出，相当于 exports.x = y;
export const a = 123;
export var b = 456;
export function c() { }
export class d { }

// 默认输出，相当于 module.exports = z;
export default function y() { }
```

但是知道这些意义并不大

这里需要注意的是module.exports和exports的区别

对这两者的区别，起源于刚开始玩node的时候，可是到现在还没细看



# module.exports 与 exports的关系
我们只需知道三点即可知道 exports 和 module.exports 的区别了：

* exports 是指向的 module.exports 的引用
* module.exports 初始值为一个空对象 {}，所以 exports 初始值也是 {}
* require() 返回的是 module.exports 而不是 exports

[exports 和 module.exports 的区别](https://cnodejs.org/topic/5231a630101e574521e45ef8)
[Understanding module.exports and exports in Node.js](https://www.sitepoint.com/understanding-module-exports-exports-node-js/)
[ES2015 & babel 实战：开发 NPM 模块](http://morning.work/page/2015-11/es6-es7-develop-npm-module-using-babel.html)




