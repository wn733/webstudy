# es6-默认参数

###es5中默认参数写法

```javascript
    function f(x,y,z){
        if(y === undefined){
            y = 7;
        }
        if(z === undefined){
            z = 42;
        }
        return x+y+z
    }
    console.log(f(1));//50  1+7+42
    console.log(f(1,3));//46 1+3+42
```

###es6中默认参数写法

```javascript
    function f(x,y=7,z=42){
        return x+y+z
    }
    console.log(f(1));//50  1+7+42
    console.log(f(1,3));//46 1+3+42
```

###es6中默认参数必选检查

```javascript
    function check(){
        throw new Error("can`t be empty")
    }
    function f(x=check(),y=7,z=42){
        return x+y+z
    }
    console.log(f(1));//50
    try{
        f()
    }catch(e){
        console.log(e); //can`t be empty
    }
```

###es5中可变参数

```javascript
    function f(){
        var a = Array.prototype.slice.call(arguments);
        var sum = 0;
        a.forEach(function(i){
            sum+=i*1
        })
        return sum
    }
    console.log(f(1,2,3,6)) //12
```

###es6中可变参数

```javascript
    function f(...a){
        var sum = 0;
        a.forEach(function(i){
            sum+=i*1
        })
        return sum
    }
    console.log(f(1,2,3,6)) //12
```
###es5扩展运算符合并

```javascript
    var params = ['hello',true,7];
    var other = [1,2].concat(params);
    console.log(other); //[1,2,'hello',true,7]
```
###es6扩展运算符合并

```javascript
    var params = ['hello',true,7];
    var other = [1,2,...params];
    console.log(other); //[1,2,'hello',true,7]
```