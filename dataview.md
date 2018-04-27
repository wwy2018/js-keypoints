# DataView
提供了对一个ArrayBuffer多种数值类型的底层读写操作接口，不需要考虑机器的字节序
* `new DataView(buffer, byteoffset, bytelength)`
## 属性
* constructor
* buffer(只读)
* bytelength(只读)
* byteoffset(只读)
* `dataview.getFloat32(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的32位数（float型）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setFloat32(1, Math.PI);

console.log(view.getFloat32(1));
// expected output: 3.1415927410125732
```
* `dataview.getFloat64(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的64位数（double型）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setFloat64(1, Math.PI);

console.log(view.getFloat64(1));
// expected output: 3.141592653589793
```
* `dataview.getInt16(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的16位短整数（short型）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setInt16(1, 32767); // (max signed 16-bit integer)

console.log(view.getInt16(1));
// expected output: 32767
```
* `dataview.getInt32(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的32位长整数（long型）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setInt32(1, 2147483647); // (max signed 32-bit integer)

console.log(view.getInt32(1));
// expected output: 2147483647
```
* `dataview.getInt8(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的8位整数（一个字节）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setInt8(1, 127); // (max signed 8-bit integer)

console.log(view.getInt8(1));
// expected output: 127
```
* `dataview.getUint32(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的无符号32位整数（无符号长整形）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setUint32(1, 4294967295); // (max unsigned 32-bit integer)

console.log(view.getUint32(1));
// expected output: 4294967295
```
* `dataview.getUint8(byteoffset, littleendian(true or false 默认true 小端序存储))`
获取相对起点偏移量位置的无符号8位整数（无符号一个字节）
```
// create an ArrayBuffer with a size in bytes
var buffer = new ArrayBuffer(16);

var view = new DataView(buffer);
view.setUint8(1, 255); // (max unsigned 8-bit integer)

console.log(view.getUint8(1));
// expected output: 255
```
以上每个get都有对应的set方法
