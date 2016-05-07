### 性能
getElementsBy系列比querySelectorAll好很多

### 使用
querySelectorAll传入的是css的表达式
可以按照css的选择器的语法去查找元素
不支持数字开头
比如，不能使用
```
querySelectorAll('.0123')
```