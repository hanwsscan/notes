### A callback is a function

#### A callback is a function that is passed as an argument to another function and is executed after its parent function has completed.

```js
//callback到处有，就是个标识，告诉你，callback的地方要写个function

function testCallback(para, callback) {
  console.log(para);
  console.log(callback);
  callback();
}

testCallback("我是参数我是参数", function() {
  console.log("我就是callback，我其实是个function(){}，匿名函数！！！！");
});

$.ajax(url, callback);
```
