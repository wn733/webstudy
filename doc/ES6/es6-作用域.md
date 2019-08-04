# es6-作用域

###es5中作用域

```javascript
    const callbacks = []
    for(var i=0;i<=2;i++){
        callbacks[i] = function(){
            return i*2 //产生闭包
        }
    }
    console.table([
        callbacks[0](), //6
        callbacks[1](), //6
        callbacks[2](), //6
    ])
```
*var定义变量提升，变成全局作用域*

###es6中作用域

```javascript
    const callbacks2 = []
    for(let j=0;j<=2;j++){
        callbacks2[j] = function(){
            return j*2
        }
    }
    console.table([
        callbacks2[0](), //0
        callbacks2[1](), //2
        callbacks2[2](), //4
    ])
```

###es5中作用域隔离

```javascript
    (function(){
        const foo = function (){
            return 1
        }
        console.log(foo() === 1);//ture
        (function(){
            const foo = function(){
                return 2
            }
            console.log(foo() === 2);//ture
        })
    })()
```

###es6中作用域隔离

```javascript
{
    function foo() {
        return 1
    }
    console.log(foo() === 1)//ture
    {
        function foo(){
            return 2
        }
        console.log(foo() === 2)//ture
    }
    console.log(foo() === 1)//ture
}

```
