准备使用vue开发自己的网站


模板中只准一个标签元素


data要返回一个对象

* 数据


* 计算属性  


* 监听属性


* 生命周期
> //     1.什么是 vue 生命周期？
vue生命周期是指vue实例对象从创建之初到销毁的过程，vue所有功能的实现都是围绕其生命周期进行的，在生命周期的不同阶段调用对应的钩子函数实现组件数据管理和DOM渲染两大重要功能。
//     2.vue生命周期的作用是什么？
vue生命周期包含4个阶段，8个钩子函数，作用在某个阶段给你一个做某些处理的机会。
//     3.第一次页面加载会触发哪几个钩子？
beforeCreate, created, beforeMount, mounted
//     4.简述每个周期具体适合哪些场景？
beforecreate : 可以在这加个loading事件，在加载实例时触发
created : 初始化完成时的事件写在这里，如在这结束loading事件，异步请求也适宜在这里调用
mounted : 挂载元素，获取到DOM节点
updated : 如果对数据统一处理，在这里写上相应函数
beforeDestroy : 可以做一个确认停止事件的确认框 nextTick : 更新数据后立即操作dom
//     5.created和mounted的区别？
created不能操作DOM节点，mounted可以操作DOM节点
//     6.vue获取数据在哪个周期函数？
created/beforeMount/mounted
//     7.请详细说下你对vue生命周期的理解？
创建前/后：在beforeCreated阶段，vue实例的挂载完el还没有。
载入前/后：在beforeMount阶段，vue实例的$el和data都初始化了，但还是挂载之前为虚拟的dom节点，data.message还未替换。在mounted阶段，vue实例挂载完成，data.message成功渲染。
更新前/后：当data变化时，会触发beforeUpdate和updated方法。
销毁前/后：在执行destroy方法后，对data的改变不会再触发周期函数，说明此时vue实例已经解除了事件监听以及和dom的绑定，但是dom结构依然存在。
