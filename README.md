# interview
🍇 这是一些与面试相关的资料收集与整理

## 基本问题（5")

1. 请简单介绍一下自己。

    我是陆康锋，是在今年7月份毕业，去年8月份来杭州开始实习的。期间我用了半年多的时间来自学前端。
2. 介绍一下你的工作经历及做过的项目，以及用到了哪些技术。

    我之前的工作是外贸，实习期大概一年时间下来觉得自己不喜欢这种类型的工作，就开始自己学习前端，我做过的项目简历上面也有粗略的介绍，这段时间我用 vue 写了一个后台管理系统。
## 基础（15")

1. 有三个元素，第一个与第三个宽度都为100px，中间元素占用剩余空间，怎么做到中间元素随着浏览器宽度的变化而变化

    1. 父元素 `display: flex；` , 中间元素 `flex: 1；` 左右两边的元素要写死宽度 100px
2. 讲讲box-sizing

    分为两种 content-box = 内容区宽度 和 border-box = 内容区宽度 + padding + border; border-left-color: black;
3. 不知宽高的垂直水平居中

    - display: flex; justify-content: center;
    - display: inline-block; vertical-align: middle;
    - 父元素 position: relative; 子元素 position: absolute; top: 50%;
4. 如何解决使用 inline-block 引起的空白间隙的问题？

    - 删去换行符和空格
    - 把父元素的 font-size 设为 0，再把子元素的 font-size 设为正常值。
5. 分别举个现实中的应用场景。使用 CSS 创建一个三角形（一个箭头向右的三角图标）。

    写一个 span 标签，``display: block; width: 0; border: 10px solid transparent``
6. 讲讲 postion 定位

    它的默认值是 static，常用的有绝对布局和 fix 布局。
7. 脱离文档流的有哪些，不脱离的有哪些？

    绝对布局和 fix 布局都是脱离文档流的
8. H5 和 CSS3 用得多么？

    计算属性 calc 及动画效果。
9. 讲讲 CSS3 属性你用哪些比较多？ 
10. 关于图片，你了解哪些形式，你觉得哪种场合用哪种？它们优劣如何？然后这些图片的应用场景能说说不？

    - jpg 有损压缩 体积小
    - png 无损压缩 体积大
    - gif 动图 体积大 渲染成本高
    - svg 图标
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

    会增加内存的使用量，由于闭包会使得函数中的变量都被保存在内存中，所以内存消耗很大解决方法思在推出函数之前，将不使用的局部变量全部删除。
18. 哪些常见操作会造成内存泄漏？
19. 如何改变 this 关键字？
20. 介bind apply call区别
21. 深浅拷贝的区别（分别有啥用户）

    举例: 假设 b 复制了 a，当修改 a 时，b 也发生了变化，则是浅拷贝，如果没有则是深拷贝。
22. 描述网页从输入url到渲染的过程 

    DNS 查询(映射 IP)，建立 TCP 连接，发送 HTTP 请求，后台处理请求，渲染 HTML 模版，发送 HTTP 响应，关闭 TCP 连接，解析 HTML，下载并解析 CSS，下载并解析 js， 渲染 DOM 树，渲染样式，执行 js。
23. 同步异步或者事件机制
24. Ajax的原理，你平常怎么发送网络请求的
25. 那你能讲下 get 和 post 请求吗？
    
    get 是读数据，post 用来写数据。
    get 的参数放在 url 的查询参数里，post 的参数放在请求消息体里。
26. 跨域通信有哪些方案，各有什么不同？

    - JSONP: 是 JSON 的一种使用模式，即跨于读取数据。通过 script 标签加载数据的方式去获取数据当作 js 代码来执行，提前在页面上声明一个函数，函数名通过接口传参的方式给后台，后台解析函数名之后在数据上包裹这个函数名发送给前端。
    - CORS: 跨域资源共享，因为 JSONP 只支持 get，所以 CORS 是大势所趋，它的特点是客户端不需要做任何特殊处理，相对简单，跨域请求分为简单请求和特殊请求，阮一峰老师有专门写过一篇博客讲这个。
27. 使用过 Promise 吗

    用 then 的方法 $.ajax().then(成功函数，失败函数)
    ```javascript
    function xxx () {
      return new Promise(function(resolve,reject) {
        setTimeout(() => {
          resolve()
          }, 3000)
      })
    }
    xxx().then()
    ```
28. 说说xss与csrf，怎么防止?

    - xss: 通过对页面注入可执行的代码（恶意的 script 标签）且成功被浏览器执行。用字符过滤方法预防。
    - csrf: 用户在浏览网页时，黑客向用户发送了一条很有吸引力的消息。用户点击之后切换到了恶意网站，这就被攻击了。预防方式是在请求地址添加 token 并验证，服务器端收到路由请求时生成一个随机数，在页面渲染时埋入页面，服务器端设置 setcookies，把该随机数作为 cookies 和 session 种入用户浏览器，当用户发送请求时带上 tocken 的参数，服务器端进行对比，相等即合法。
## 针对简历问（15")

1. 会ES6吗，什么是解构赋值？
2. 其他 ES6 语法你用过吗

    - class
    - let/const
    - 字符串模版 `${}`
3. 主流前端框架如 Angular/React/Vue 等之间有哪些差异及特点，选取一个描述其组件生命周期。

    - vue 是一个渐进式的前端框架，它提供了许多例如 computed、method、watch等 api，并且运用组件化的思想，将一个大文件拆分成各个小组件，便于我们书写和后期的维护。它的生命周期有 beforecreate、created、beforemount、mounted、beforeupdate、updated、beforedestory、destoryed、activated、deactivated、errcaptured。
4. 讲下 v-if 与 v-show 的区别吗

    - v-if: 直接删除 dom 上相关节点
    - v-show: 只修改了 css样式 display: none
5. v-for 你使用过程中，有遇到什么问题或者关注点吗
6. v-bind:class 有使用过吗？有什么要注意的吗？
7. 组件之间的传值通信？

    - 父子组件通信使用 prop 传递数据，v-on 绑定自定义事件。自组件调用父组件 $emit()
    - 非父子通信 用 new vue() 作 eventbus()
8. vuex

    专为 vue 开发的状态管理程序，集中管理所有组件的状态，并以相应规则发生变化。
9. Vue hash 路由和 history 路由的区别

    history 路由需要 ngnix 特殊配制一下。
10. 虚拟dom

    
11. JS 基础考察

    有如下代码
    ```javascript
    function fn(){
        return 1
    }
    ```
    请问 fn 和 fn() 的区别是什么？
    
    fn 是指一个函数声明，fn() 是指调用这个函数。
12. JS 基础考察

    有如下代码
    ```javascript
    var name = 'x'
    var obj = {
        name: 'frank'
    }
    ```
    请问 obj[name] 的值是多少？
    
    undefined
13. JS 基础考察

    有如下代码
    ```javascript
    var a = [1,2,3]
    ```
    请问，a.concat(4) 与 a.push(4) 的区别是什么？
    - concat() 用于连接两个或多个数组，并返回新的数组。
    - push() 向数组末尾添加一个或者多个元素并返回新数组的长度。
14. JS 基础考察

    有如下未完成的代码
    ```javascript
    Array.prototype.self = function(){
      //未完成
    }
    let arr = [1,2,3,4,5]
    arr.self() // [1,2,3,4,5]
    ```
    请填写未完成的部分，使得 arr.self() 的值是 [1,2,3,4,5]
15. JS 基础考察JS 有哪几种数据类型？

    string bool symbol number object undefind null
16. debounce 和 throttle 的使用场景分别是什么？简单实现一个 debounce 或者 throttle。
17. map reducer filter 各自有什么作用

    - map 入参是函数，返回一个新数组，数组中的每个元素是被函数处理后的值。
    - reducer 入参是函数，数组中每个元素执行完函数之后将结果汇总为单个返回值。
    - filter 入参是函数，返回一个新数组，数组中的元素通过函数的测试。
    
18. 讲一个你遇到的比较有困难的问题 你是怎么解决他的
19. 一个 web 项目如何做性能优化

    不要过早优化性能，如果一定要优化，一定是在有数据支撑的情况下，先收集用户的使用数据（sentry 平台），比如首屏加载时间，然后如果是资源请求速度过慢，可以考虑使用 cdn，如果是其他问题，就从前端工程化的角度去解决。
20. 用 React 写一个 Hello World（要求能运行，你可以使用 jsbin.com 或者 codesandbox.io 或者 GitHub Pages 来写）如果你想看起来比其他应聘者厉害，你可以加各种其他的东西。
21. 用 Vue 写一个 Hello World（要求能运行，你可以使用 jsbin.com 或者 codesandbox.io 或者 GitHub Pages 来写）如果你想看起来比其他应聘者厉害，你可以加各种其他的东西。
22. 写出你觉得厉害的程序员的名字或者开源项目的名字，并说出理由，不少于五个。

## 收尾（5")
1. 有没有开源项目的参与经历？
2. 你有什么想问我们的问题吗？

    请问工作是否需要出差
