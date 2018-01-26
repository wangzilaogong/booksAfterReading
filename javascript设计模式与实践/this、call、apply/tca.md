# this的指向
1. this作为对象的方法调用->obj
```javascript
var obj = {
    a:1,
    getA :function(){
        alert(this === obj);    //true
        alert(this.a);          // 1
    }
}
obj.getA();
```
2. 作为普通的函数里调用->window
```javascript
window.name = 'globalName';
var getName = function(){
    return this.name;
}
console.log(getName());

// !!!
var myObject = {
    name :'seven',
    getName:function(){
        return this.name ;
    }
}
var getName = myObject.getName;
console.log(myObject.getName()); //seven
console.log(getName()); // globalName

```



