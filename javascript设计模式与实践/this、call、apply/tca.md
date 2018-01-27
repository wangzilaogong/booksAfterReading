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
2. this作为普通的函数里调用->window
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
3. this作为构造器调用->obj or 返回的obj
```javascript
    var myClass = function(){
        this.name = 'seven';
    }
    var obj = new myClass();
    alert(obj.name);//seven

    var myClass2 = new function(){//显式返回一个对象
        this.name = 'seven';
        return {
            name :'anne'
        }
    }
    var obj = new myClass2();
    alert(obj.name)//anne
```
4. Function.prototype.call 或 Function.prototype.apply 动态调用
```javascript
    var obj1 = {
        name :'seven',
        getName :function(){
            return this.name;
        }
    }
     var obj2 = {
        name :'anne',
    }
    console.log(obj1.getName()); //seven
    console.log(obj1.getName.call(obj2)); //anne
```
# 丢失的this
```javascript
    var obj = {
        myName : 'seven',
        getName :function(){
            return this.name;
        }
    };
    console.log(ovj.getName());//seven
    var getName2 = obj.getName;
    console.log(getName2()) //undefined 这边的调用是普通函数。window对象
```




