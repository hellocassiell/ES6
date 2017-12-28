# ES6

## let和const
### let
- let 所声明的变量，只在let命令所在的**代码块内**有效。
- let 不存在变量提升
```
// var 的情况
console.log(foo); // 输出undefined
var foo = 2;

// let 的情况
console.log(bar); // 报错ReferenceError
let bar = 2;
```

- let 暂时性死区
只要块级作用域内存在let命令，它所声明的变量就“绑定”（binding）这个区域，不再受外部的影响。
在代码块内，使用let命令**声明变量之前**，该变量都是**不可用**的。
```
var tmp = 123;

if (true) {
  tmp = 'abc'; // ReferenceError
  let tmp;
}
```
- let 不允许重复声明
let不允许在相同作用域内，重复声明同一个变量。
因此，不能在函数内部重新声明参数。
```
// 报错
function func() {
  let a = 10;
  var a = 1;
}
function func(arg) {
  let arg; // 报错
}

function func(arg) {
  {
    let arg; // 不报错
  }
}
```

#### 块级作用域
ES5 规定，函数只能在顶层作用域和函数作用域之中声明，不能在块级作用域声明。
但是，浏览器没有遵守这个规定，为了兼容以前的旧代码，还是支持在块级作用域之中声明函数
ES6 引入了块级作用域，明确允许在块级作用域之中声明函数。ES6 规定，块级作用域之中，函数声明语句的行为类似于let，在块级作用域之外不可引用。

### const 
const声明一个**只读**的常量。一旦声明，常量的值就不能改变
const一旦声明变量，就必须立即初始化，不能留到以后赋值。
const  只在声明所在的块级作用域内有效;不提升;存在暂时性死区
```
const PI = 3.1415;
PI // 3.1415

PI = 3;
// TypeError: Assignment to constant variable.
```

##### es6声明变量的六种方法
var function let const import class
ES5 只有两种声明变量的方法：var命令和function命令
## 数值的扩展
Number.isNaN()    检测一个值是否为NaN
