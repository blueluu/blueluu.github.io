---
layout: post
title:  "vue watch 深度监听"
date:   2017-11-9 18:03:09
categories: vue
---
##### watch{} 对象，深度监听

=====================

- 目的：watch虽然可以监听，但是只能监听第一层或者第二层；
- 什么是第二层，例如：
```
let obj = {
    name: 'Jane',
    firend: {
        name: 'Bob',
        age: 11
    }
}
``` 
*firend之后到值就是第二层或者深层  
- 实现目标：如果要监听一个对象中的属性，属性最高也是第二层了，watch可能监听不到，所有要使用深度监听
- 实现代码：
```
watch:{
    c: {
      handler: function (val, oldVal) { /* ... */ },
      deep: true
      //特别注意，不能用箭头函数，箭头函数，this指向全局
		处理函数
    },
}
```


=====================
