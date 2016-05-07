childNodes会包含所有类型的node，比如text node，comment node

children只会包含element类型的child

```
var el = document.createElement("div");
el.textContent = "foo"
el.childNodes.length === 1; // TextNode is a node child
el.children.length === 0; // no Element children
```

children是DOM4里面的，现在支持的浏览器并不好，但是如果想用，可以使用[DOM-shim](https://github.com/Raynos/DOM-shim)

我们其实很多时候想使用的也是children, 毕竟有时我们不想便利到text node之类的

### 资料

http://stackoverflow.com/questions/7935689/what-is-the-difference-between-children-and-childnodes-in-javascript