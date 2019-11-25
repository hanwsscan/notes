### 有了模块，我们就可以更方便地使用别人的代码，想要什么功能，就加载什么模块

```
(function() {}())
```

### CommonJS，AMD，CMD

#### CommonJS API 定义很多普通应用程序（主要指非浏览器的应用）使用的 API

```
它的终极目标是提供一个类似Python，Ruby和Java标准库。这样的话，开发者可以使用CommonJS API编写应用程序，然后这些应用可以运行在不同的JavaScript解释器和不同的主机环境中。

在兼容CommonJS的系统中，你可以使用JavaScript开发以下程序：

(1).服务器端JavaScript应用程序
(2).命令行工具
(3).图形界面应用程序
(4).混合应用程序（如，Titanium或Adobe AIR）
```

#### NodeJS 是 CommonJS 规范的实现，webpack 也是以 CommonJS 的形式来书写。

```
在CommonJS中，有一个全局性方法require()，用于加载模块。假定有一个数学模块math.js，就可以像下面这样加载。

CommonJS定义的模块分为:{模块引用(require)} {模块定义(exports)} {模块标识(module)}

require()用来引入外部模块；
exports对象用于导出当前模块的方法或变量，唯一的导出口；
module对象就代表模块本身。

```

```js
var math = require("math");
math.add(2, 3); // 5
```

#### AMD 规范诞生的背景 同步加载 异步模块

```
CommonJS规范不适用于浏览器环境

服务器端所有的模块都存放在本地硬盘，可以同步加载完成，等待时间就是硬盘的读取时间。但是，对于浏览器，这却是一个大问题，因为模块都放在服务器端，等待时间取决于网速的快慢，可能要等很长时间，浏览器处于"假死"状态

浏览器端的模块，不能采用"同步加载"（synchronous），只能采用"异步加载"（asynchronous）。这就是AMD规范诞生的背景。

CommonJS是主要为了JS在后端的表现制定的，他是不适合前端的，AMD(异步模块定义)出现了，它就主要为前端JS的表现制定规范。

AMD是"Asynchronous Module Definition"的缩写，意思就是"异步模块定义"。它采用异步方式加载模块，模块的加载不影响它后面语句的运行。所有依赖这个模块的语句，都定义在一个回调函数中，等到加载完成之后，这个回调函数才会运行
```

##### AMD 也采用 require()语句加载模块，但是不同于 CommonJS，它要求两个参数

```js
// math.js
define(function() {
  var add = function(x, y) {
    return x + y;
  };

  return {
    add: add
  };
});
```

```js
// require([module], callback);
require(["math"], function(math) {
  math.add(2, 3);
});

// main.js
// require()异步加载moduleA，moduleB和moduleC，浏览器不会失去响应；它指定的回调函数，只有前面的模块都加载成功后，才会运行，解决了依赖性的问题
require(["moduleA", "moduleB", "moduleC"], function(moduleA, moduleB, moduleC) {
  // some code here
});
```
