new 运算符创建一个用户定义的对象类型的实例或具有构造函数的内置对象类型之一

1：创建空对象
2: 将函数原型赋给对象
3: apply
4:返回对象

 function objectFactory(Constructor,...remain) {

       var obj = new Object()



       obj.__proto__ = Constructor.prototype;

       Constructor.apply(obj, ...remain);

      return typeof ret === 'object' ? ret : obj;

   }
