# Promise
promise对象代表了一个异步操作的最终状态（完成或失败）以及结果值<br>
promise构造函数主要用于包裹非promise函数
```
new Promise( /* executor */ function(resolve, reject) { ... } );
```
executor函数接受resolve和reject两个参数，executor函数立即执行，并在promise对象新建之前调用，executor通常初始化异步操作。