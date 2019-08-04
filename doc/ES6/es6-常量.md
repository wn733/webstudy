# es6-常量

###es5中的常量写法

```javascript
    Object.defineProperty(window,"PI2",{
        value:3.1415926,
        writable:false  //只读模式
    })
```

###es6中常量中的写法
```javascript
    const PI2 = 3.1415926
```