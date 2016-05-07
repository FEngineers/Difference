On the Introduction to events page I asked a question that at first sight seems incomprehensible: 
“If an element and one of its ancestors have an event handler for the same event, which one should fire first?” Not surprisingly, this depends on the browser.

The basic problem is very simple. Suppose you have a element inside an element

### 事件的发生顺序
这个问题的起源非常简单，假设你在一个元素中又嵌套了另一个元素
```
-----------------------------------
| element1                        |
|   -------------------------     |
|   |element2               |     |
|   -------------------------     |
|                                 |
-----------------------------------
```
并且两者都有一个onClick事件处理函数(event handler)。如果用户单击元素2，则元素1和元素2的单击事件都会被触发。
但是哪一个事件先被触发？哪一个事件处理函数会被首先执行？
换句话说，事件的发生顺序到底如何？



### addEventListener
什么时候要传入第三个参数，什么时候应该false，什么时候应该true

* true: 捕获阶段
* false: 冒泡阶段


### 参考或转载
http://www.quirksmode.org/js/events_order.html
http://blog.jobbole.com/39446/