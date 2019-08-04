# es6-箭头函数

```javascript
//箭头函数形式
()=>{

}
```

###es5中遍历

```javascript
    var evens = [1,2,3,4,5];
    var odds = evens.map(function(v){
        return v+1
    })
    console.log(evens,odds);//[1,2,3,4,5]  [2,3,4,5,6]
```

###es6中遍历
```javascript
    let evens = [1,2,3,4,5];
    let odds = evens.map( v => v+1 );
    console.log(evens,odds);//[1,2,3,4,5]  [2,3,4,5,6]
```

###es5this的制向

```javascript
    var factory = function (){
        this.a = 'a',
        this.b = 'b',
        this.c = {
            a:'a+',
            b:function(){
                return this.a
            }
        }
    }
    console.log(new factory().c.b()); //a+
```
*this的指向是该函数被调用的对象*

###es6this的制向

```javascript
    var factory = function (){
        this.a = 'a',
        this.b = 'b',
        this.c = {
            a:'a+',
            b:() => {
                return this.a
            }
        }
    }
    console.log(new factory().c.b()); //a
```
*箭头函数中this的指向是定义时this的指向*