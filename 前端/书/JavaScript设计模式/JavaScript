#第一章JavaScript

##尽量少的创建全局变量（放在对象或函数里）
```js
const CheckObject = function(){};
CheckObject.prototype = {
   checkName: function(){
      //验证姓名
      return this
   }，
   checkEmail: function(){
      //验证邮箱
      return this
   }
}

const a = new CheckObject()
a.checkName().checkEmail()
如此可链式调用
```

源生对象的拓展
```js
Function.prototype.addMethod = function(name, fn){
  this.[name] = fn;
  return this
}
const methods = function(){};
methods.addMethod(`checkName`, function(){
  //验证姓名
}).addMethods(`checkEmail`, function(){
  //验证邮箱
})

//new
Function.prototype.addMethod = function(name, fn){
  this.prototype[name] = fn;
  return this
}
const methods = function(){};
methods.addMethod(`checkName`, function(){
  //验证姓名
}).addMethods(`checkEmail`, function(){
  //验证邮箱
})
const m = new Methods();

