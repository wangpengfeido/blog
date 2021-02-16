先上结论：

用 new 执行构造器函数时:1.若构造器函数没有返回值，则默认返回 this；2.若构造器函数返回非对象的值，则返回 this；3.若构造器函数返回对象，则返回该对象

```javascript
var Test1 = function () {
  this.name = "wang";
  return { birth: "1995" };
};
Test1.prototype.phone = "12345";
console.log(new Test1());

var Test2 = function () {
  this.name = "wang";
  return "hello";
};
Test2.prototype.phone = "12345";
console.log(new Test2());
```

第一部分代码返回一个带有 birth 属性的对象，但没有 name 属性和 phone 属性。若将返回值注释掉，则返回带有 name 和 phone 属性的对象，但没有 birth 属性

第二部分代码返回带有 name 和 phone 属性的对象。返回的字符串并没有卵用。

此结论在 ES6 中 class 的 constructor 函数同样适用
