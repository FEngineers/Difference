> 这篇内容主要转载自[详解 CSS 属性 - 伪类和伪元素的区别](https://segmentfault.com/a/1190000000484493)

如果有问题，可以随时联系我删除

首先，阅读 w3c 对两者的定义：
* CSS 伪类用于向某些选择器添加特殊的效果。
* CSS 伪元素用于将特殊的效果添加到某些选择器。

### 伪类
:active
:focus
:hover
:link
:visited
:first-child

### 伪元素
::after
::before
::first-letter
::first-line
::selection
::backdrop

### 区别
选择first-child和first-letter来比较

```
p>i:first-child {color: red}
<p>
    <i>first</i>
    <i>second</i>
</p>
```
结果是"first"变红

如果我们不使用伪类，而希望达到上述效果，可以这样做：

```
.first-child {color: red}
<p>
    <i class="first-child">first</i>
    <i>second</i>
</p>
```

即我们给第一个子元素添加一个类，然后定义这个类的样式。那么我们接着看看为元素：
```
p:first-letter {color: red}
<p>I am stephen lee.</p>
```
结果是"I"变红

那么如果我们不使用伪元素，要达到上述效果，应该怎么做呢？

```
.first-letter {color: red}
<p><span class='first-letter'>I</span> am stephen lee.</p>
```

即我们给第一个字母添加一个 span，然后给 span 增加样式。
两者的区别已经出来了。那就是：

> 伪类的效果可以通过添加一个实际的类来达到，而伪元素的效果则需要通过添加一个实际的元素才能达到，这也是为什么他们一个称为伪类，一个称为伪元素的原因。


### 资料
[详解 CSS 属性 - 伪类和伪元素的区别](https://segmentfault.com/a/1190000000484493)

[伪元素](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements)

[伪类](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes)

