- JavaScript引擎内部有个执行上下文栈(Execution Context Stack, ECS),用于执行代码的调用栈
- 一开始是执行全局代码块,创建一个全局执行上下文,放入执行上下文栈中
- 在执行全局代码块之前,会创建一个全局对象:Global Object(GO)
  - 该对象所有作用域都可以访问
  - 包括:Date,string,Array,Number,setTimeout, setInterval
  - 包括一个window属性指向自己

- 遇到执行函数时,就创建一个新的函数执行上下文(Functional Execution Context),压入执行上下文栈中
- 在执行当前栈顶的执行上下文时,会创建一个新的VO(variable object),关联到当前执行上下文
- 执行完成后,栈顶执行上下文弹出,继续执行下一个执行上下文
- 直到全局执行上下文执行完毕