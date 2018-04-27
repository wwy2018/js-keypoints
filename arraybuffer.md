# 流数组
表示固定长度的二进制数据缓冲区。<br>
属性有：byteLength, isView, slice<br>
不能对流数组进行直接操作，需要通过流数组生成类型化数组或者DataView，对流进行操作
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(8);

console.log(buffer.byteLength);
// expected output: 8
```
isView(arg) 用于判断arg是否是类型化数组或者dataview
```
ArrayBuffer.isView(new Int8Array())
// true
```
