function testCallback(para, callback) {
  console.log(para);
  console.log(callback);  
}

testCallback("我是参数我是参数", function() {
  console.log("我就是callback，我其实是个function(){}，匿名函数！！！！");
});


testCallback("我是参数我是参数", function() {
  console.log("我就是callback，我其实是个function(){}，匿名函数！！！！");
});