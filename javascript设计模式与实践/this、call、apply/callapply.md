    # call & apply
    * 区别：仅仅在于参数形式不一样 call其实是apply 的语法糖
    ```javascript
    var func  = function(a,b,c){
        alert([a,b,c])
    }
    func.call(null,1,2,3)//null 让函数体内的this指向默认的宿主对象 浏览器里就是window，但是再严格模式下就是null
    ```
    * 用途
    1. 修改this 指向 实际开发中
    ```javascript
        document.getElementById('div1').onclick = function(){
            alert(this.id);//div1
            var func = function(){
                alert(this.id); //undefined
            }
            func();
        }
        //修改之后
        document.getElementById('div1').onclick = function(){
            alert(this.id);//div1
            var func = function(){
                alert(this.id); //div1
            }
            func.call(this);//此处用call修正this指向
        }
    ```
    2. bind函数
    ```javascript
        Function.prototype.bind = function(){
            var self = this;
            console.log(self);
            return function(){
                return self.apply(context,arguments);
            }
        };

        var obj = {
            name:'sven'
        }

        var func = function(){
            alert(this.name);
        }.bind(obj);

        func();

        // 复杂下
        Function.prototype.bind = function(){
            var self = this;
            context = [].shift.call(arguments);//this目标
            args = [].slice.call(arguments);
            return function(){
                return self.apply(context,[].concat.call(args,[].slice.call(arguments)));//合并剩余参数
            }
        }

        var obj2 ={
            name:'wk'
        }

        var func2 = function(){
            alert(this.name);
            alert([a,b,c,d]);
        }.bind(obj2,1,2);

        func2(3,4);
    ```
    3. 借用其他的对象的方法
    * 借用构造函数 
    ```javascript

        var A = function(name){
            this.name = name;
        }
        var B = function(){
            A.apply(this,arguments);
        }
        B.prototype.getName = function(){
            return this.name;
        }
        var b = new B("wk");
        console.log(b.getName());//wk 类似继承的

        //借用方法
        (function(){
            Array.prototype.push.call(arguments,3);
            console.log(arguments);//[1,2,3]
        })(1,2)
    ```
