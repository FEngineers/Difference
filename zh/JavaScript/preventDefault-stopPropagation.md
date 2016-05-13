[stopPropagation, preventDefault 和 return false 的区别](http://www.neoease.com/stoppropagation-and-preventdefault-and-return-false/)

# Event.preventDefault()
> Cancels the event if it is cancelable, without stopping further propagation of the event.

一个带事件监听的链接代码如下:
```
<a href="http://w3c.org" onclick="alert('JavaScript Click Event');">点击链接</a>
```

点击该链接, 显示对话框后跳转页面. 由此可知, 除了执行监听事件还会触发浏览器默认动作; 执行监听事件在前, 触发浏览器默认动作在后.

这里有个经典示例, 我们希望点击链接在新窗口打开页面, 但不希望当前页面跳转. 
这个时候可以使用 preventDefault() 阻止后面将要执行的浏览器默认动作.

```
<a id="link" href="http://w3c.org">W3C 首页链接</a>
 
<script>
// 在新窗口, 打开页面
document.getElementById('link').onclick = function(ev) {
	// 阻止浏览器默认动作 (页面跳转)
	ev.preventDefault();
	// 在新窗口打开页面
	window.open(this.href);
};
</script>
```

# Event.stopPropagation()
> Prevents further propagation of the current event in the bubbling phase.

假设页面上存在一个浮动弹出层, 显示在最前面, 当点击弹出层以外页面区域时, 隐藏弹出层. 
为了做到这样的效果, 我们会监听 documentElement 的 click 事件, 一旦事件被触发即隐藏弹出层. 但是...

这显然存在问题. 当用户点击弹出层时, 我们不希望它隐藏掉. 
但因为事件的冒泡传递, documentElement 的 click 事件也会被触发. 
这个时候, 我们可以监听弹出层的 click 事件, 并使用 stopPropagation() 方法阻止冒泡. 请参考下面的代码.

```
// 在弹出对话框上点击时, 不进行任何页面操作, 并阻止冒泡
document.getElementById('dialog').onclick = function(ev) {
	ev.stopPropagation();
};

// 在 documentElement 节点上监听到点击事件时, 隐藏对话框
document.documentElement.onclick = function(ev) {
	document.getElementById('dialog').style.display = 'none';
};
```

