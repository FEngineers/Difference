# flux
简单说，Flux 是一种架构思想，专门解决软件的结构问题。它跟MVC 架构是同一类东西，但是更加简单和清晰。

Flux 的最大特点，就是数据的"单向流动"。

### View： 视图层
### Action（动作）：视图层发出的消息（比如mouseClick）
### Dispatcher（派发器）：用来接收Actions、执行回调函数
### Store（数据层）：用来存放应用的状态，一旦发生变动，就提醒Views要更新页面
