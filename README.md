# interview
🍇 这是一些与面试相关的资料收集与整理

## 基本问题（5")

1. 请简单介绍一下自己。

    我是陆康锋，是在今年7月份毕业，去年8月份来杭州开始实习的。期间我用了半年多的时间来自学前端。
2. 介绍一下你的工作经历及做过的项目，以及用到了哪些技术。

    我之前的工作是外贸，后来自己不喜欢这种类型的工作，就开始自己学习前端，我做过的项目简历上面也有粗略的介绍，这段时间我用 vue 写了一个后台管理系统。
## 基础（15")

1. 有三个元素，第一个与第三个宽度都为100px，中间元素占用剩余空间，怎么做到中间元素随着浏览器宽度的变化而变化

    父元素 ``display: flex；`` , 中间元素 ``flex: 1；``
2. 讲讲box-sizing

    分为两种 content-box = 内容区宽度 和 border-box = 内容区宽度 + padding + border; border-left-color: black;
3. 不知宽高的垂直水平居中

    - display: flex; justify-content: center;
    - display: inline-block; vertical-align: middle;
    - 父元素 position: relative; 子元素 position: absolute; top: 50%;
4. 如何解决使用 inline-block 引起的空白间隙的问题？
5. 分别举个现实中的应用场景。使用 CSS 创建一个三角形（一个箭头向右的三角图标）。

    写一个 span 标签，``display: block; width: 0; border: 10px solid transparent``
6. 讲讲 postion 定位
7. 脱离文档流的有哪些，不脱离的有哪些
8. H5 和 CSS3 用得多么？
9. 讲讲 CSS3 属性你用哪些比较多？ 
10. 关于图片，你了解哪些形式，你觉得哪种场合用哪种？它们优劣如何？然后这些图片的应用场景能说说不？
11. 了解过缓存这些吗
12. 什么场景使用那些技术？
13. 那 LocalStorage 会根据时间清空吗？还是会一直存在浏览器上？

    会一直在存浏览器上。
14. 有一个长度为 100 的数组，请求出该数组的前 10 个元素之和。

    ```javascript
    var sum = 0
    for(var i = 0; i < 10; i++) {
      var a = array[i]
      sum += a
    }
    ```
15. 写一个程序打印 1 到 100 这些数字，遇到数字为 3 的倍数，打印 “A” 替代该数字；遇到 5 的倍数，用 “B” 代替；遇到即是 3 的倍数又是 5 的倍数，打印 “AB”。

    ```javascript
    for(var i = 1; i <= 100; i++) {
      var num = i
      if(i % 3 === 0) {
        console.log('A')
      } else if (i % 5 === 0) {
        console.log('B')
      } else if (i % 3 === 0 && i % 5 === 0) {
        console.log('AB')
      }
      console.log(i)
    }
    ```
16. 一句话介绍下 JavaScript 的闭包、原型链和 this 关键字吧

    - 闭包: 函数和函数内部能访问到的变量的总和就是闭包
    - 原型链: 每个对象都有 proto 属性，并指向他的 prototype 原型对象，而 prototype 原型又具有自己的 prototype 原型对象，就这么一直往上直到一个对象的原型 prototype 为 null。
    - this 关键词: 
17. 闭包缺点？
18. 哪些常见操作会造成内存泄漏？
19. 如何改变 this 关键字？
20. 介bind apply call区别
21. 深浅拷贝的区别（分别有啥用户）
22. 描述网页从输入url到渲染的过程 
23. 同步异步或者事件机制
24. Ajax的原理，你平常怎么发送网络请求的
25. 那你能讲下 get 和 post 请求吗？
    
    get 是读数据，post 用来写数据。
    get 的参数放在 url 的查询参数里，post 的参数放在请求消息体里。
26. 跨域通信有哪些方案，各有什么不同？

    - JSONP: 是 JSON 的一种使用模式，即跨于读取数据。通过 script 标签加载数据的方式去获取数据当作 js 代码来执行，提前在页面上声明一个函数，函数名通过接口传参的方式给后台，后台解析函数名之后在数据上包裹这个函数名发送给前端。
    - CORS: 跨域资源共享，因为 JSONP 只支持 get，所以 CORS 是大势所趋，它的特点是客户端不需要做任何特殊处理，相对简单，跨域请求分为简单请求和特殊请求，阮一峰老师有专门写过一篇博客讲这个。
27. 使用过 Promise 吗
28. 说说xss与csrf，怎么防止?

    - xss: 
    - csrf: 
## 针对简历问（15")

1. 会ES6吗，什么是解构赋值？
2. 其他 ES6 语法你用过吗
3. 主流前端框架如 Angular/React/Vue 等之间有哪些差异及特点，选取一个描述其组件生命周期。
4. 讲下 v-if 与 v-show 的区别吗
5. v-for 你使用过程中，有遇到什么问题或者关注点吗
6. v-bind:class 有使用过吗？有什么要注意的吗？
7. 组件之间的传值通信？
8. vuex
9. Vue hash 路由和 history 路由的区别
10. 虚拟dom
11. JS 基础考察
    有如下代码
    ```javascript
    function fn(){
        return 1
    }
    ```
    请问 fn 和 fn() 的区别是什么？
12. JS 基础考察有如下代码
    ```javascript
    var name = 'x'
    var obj = {
        name: 'frank'
    }
    ```
    请问 obj[name] 的值是多少？
13. JS 基础考察有如下代码
    ```javascript
    var a = [1,2,3]
    ```
    请问，a.concat(4) 与 a.push(4) 的区别是什么？
14. JS 基础考察有如下未完成的代码
    ```javascript
    Array.prototype.self = function(){
      //未完成
    }
    let arr = [1,2,3,4,5]
    arr.self() // [1,2,3,4,5]
    ```
    请填写未完成的部分，使得 arr.self() 的值是 [1,2,3,4,5]
15. JS 基础考察JS 有哪几种数据类型？
16. debounce 和 throttle 的使用场景分别是什么？简单实现一个 debounce 或者 throttle。
17. map reducer filter 各自有什么作用
18. 讲一个你遇到的比较有困难的问题 你是怎么解决他的
19. 一个 web 项目如何做性能优化
20. 用 React 写一个 Hello World（要求能运行，你可以使用 jsbin.com 或者 codesandbox.io 或者 GitHub Pages 来写）如果你想看起来比其他应聘者厉害，你可以加各种其他的东西。
21. 用 Vue 写一个 Hello World（要求能运行，你可以使用 jsbin.com 或者 codesandbox.io 或者 GitHub Pages 来写）如果你想看起来比其他应聘者厉害，你可以加各种其他的东西。
22. 写出你觉得厉害的程序员的名字或者开源项目的名字，并说出理由，不少于五个。

## 收尾（5")
1. 有没有开源项目的参与经历？
2. 你有什么想问我们的问题吗？

    请问工作是否需要出差呢？其他问题就暂时没有了关于贵司我也有在网上了解过。
