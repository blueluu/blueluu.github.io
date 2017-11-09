---
layout: post
title:  "vue watch 深度监听"
date:   2017-11-9 18:03:09
categories: vue
---
watch:{} 对象，可监听数据，数据发生变化， 处理函数

目的： watch虽可监听，但只是浅监听，只监听数据第一层或者第二层，
什么是第二层？
 let obj = {name: 'xx', child: {age: 11}};
  child之后的值就为第二层或者深层
实现目标:  
   如果要监听一个对象中的属性，属性最高也是第二层了，watch可能监听不到，
 所有要使用深度监听：

实现代码:
watch: {
	' user.phone ' : {
		handel:function(){//特别注意，不能用箭头函数，箭头函数，this指向全局
		处理函数
		},
		deep: true    //深度监听
	}
}

=====================
