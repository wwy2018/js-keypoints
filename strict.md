严格模式相对普通模式在语义上有一些改变：
* js的静默错误会报错
* 纠正阻碍js引擎优化的错误，提高运行速度
* 阻止使用可能被将来ecmascript版本定义的语法

ie10以下不支持严格模式，所以严格模式下的代码需要做兼通测试
# 使用方法
在脚本第一行添加`use strict`（不在第一行添加无效），之后的代码就会被严格模式所约束，也可以在函数中单独添加(不在第一行添加无效)
# 严格模式的代码要求
> 明确定义变量，不能省略关键字
> 不可以的全局变量不能作为变量名，例如：NaN, non-extensible对象
```
NaN = 1
console.log(NaN) // 报错
```
```
var NaN = 1
console.log(NaN) // 1
```
> 试图删除不可删除属性时报错
```
'use strict';
delete Object.prototype; // throws a TypeError
```
> 对象属性名唯一（es6之前）
> 函数参数名唯一
> 禁止八进制，es6支持前缀`0o`表示八进制
```
var sum = 015 // !!! 语法错误
```
```
var a = 0o10; // ES6: 八进制
```
> 进制在原始类型值上添加属性
```
(function() {
'use strict';

false.true = '';         // TypeError
(14).sailing = 'home';     // TypeError
'with'.you = 'far away'; // TypeError

})();
```
> 严格模式禁止使用with
> eval内的变量为局部变量，不影响外层变量
```
var x = 17;
var evalX = eval("'use strict'; var x = 42; x");
console.assert(x === 17);
console.assert(evalX === 42);
```
> 禁止删除声明变量
```
'use strict';

var x;
delete x; // !!! syntax error

eval('var y; delete y;'); // !!! syntax error
```
> eval和arguments不能作为变量名称，严格模式下不能通过arguments改变参数值，不再支持arguments.callee, arguments.caller
> this不再被封装为对象，而且如果没有指定this的话它的值是undefined
```
"use strict";
function fun() { return this; }
console.assert(fun() === undefined);
console.assert(fun.call(2) === 2);
console.assert(fun.apply(null) === null);
console.assert(fun.call(undefined) === undefined);
console.assert(fun.bind(true)() === true);
```
> 不支持fun.caller, fun.callee, fun.arguments
> 字符implements, interface, let, package, private, protected, public, static和yield不能作为变量名或者形参名。