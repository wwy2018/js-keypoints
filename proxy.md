# Proxy
> Proxy是一个对象，用于对一些基础方法进行自定义
## 术语概念
> handler: 包含拦截方法的占位对象

> traps: 拦截方法

> target: 目标拦截对象

## `new Proxy(target, handler)`
* target：可以是任何类型的对象，包括数组，函数，或者另外一个proxy
* handler：定义拦截方法的对象
---
### 方法
> Proxy.revocable()：创建一个可撤销的proxy对象
### handler中的拦截方法
* handler.getPrototypeOf()：Object.getPrototypeOf的拦截方法.
* handler.setPrototypeOf()：Object.setPrototypeOf的拦截方法.
* handler.isExtensible()：Object.isExtensible的拦截方法.
* handler.preventExtensions()：Object.preventExtensions的拦截方法.
* handler.getOwnPropertyDescriptor()：Object.getOwnPropertyDescriptor的拦截方法.
* handler.defineProperty()：Object.defineProperty的拦截方法.
* handler.has()：`in`操作符的拦截方法.
* handler.get()：获取属性值的拦截方法.
* handler.set()：设置属性值的拦截方法.
* handler.deleteProperty()：删除操作的拦截方法.
* handler.ownKeys()：Object.getOwnPropertyNames和Object.getOwnPropertySymbols的拦截方法.
* handler.apply()：函数call的拦截方法
```
var p = new Proxy(target, {
  apply: function(target, thisArg, argumentsList) {
  }
});

target: 目标对象，必须是函数<br>
thisarg：调用时的执行上下文<br>
argumentslist：调用时的参数数组
```
* handler.construct()：`new`操作的拦截方法.
```
var p = new Proxy(target, {
  construct: function(target, argumentsList, newTarget) {
  }
});

target：必须具有有效的constructor，可供new操作

argumentslist：参数

newtTarget：新创建的对象

construct必须返回一个对象
```
