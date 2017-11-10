# h2 面试
## 内容
### 1. 完整javascript代码，实现1x2+2x3+3x4+4x5........96x97+97x98+98x99+99x100x101结果?  
```js
    //方法一:
      function   Sum (n) {
        let num = 0;
        for(let i=1;i<(n-1);i++){
          num += i*(i+1);
        };
        return num + n*(n-1)*(n+1);
      };
    console.log(Sum(100)) //结果: 1323300

   //方法二:

    function SS(m) {
      function S (n) {
        if(n==2) {
          console.log("1 x 2");
          return 1*2;
        };
        return (n-1)*n + S(n-1);
      };
      return S(m-1) + m*(m-1)*(m+1);
    }

  console.log(SS(100)); // 结果: 1323300
```

### 2. 排序有哪些方法，用javascript实现其中一个排序的方法？




### 3. 用javascript 方法使数组去重?
```js
  /*
    功能: 实现数组去重
    array: 要去重的数组
  */

  function filterSame ( array) {
    if(!Array.isArray(array)) {
      return array
    }
    let newarray =[];
    for (let i in array) {
      if(newarray.includes(array[i]) == false) {
        newarray.push(array[i]);
      }
    }
    return newarray;
  }

  const a = [1,2,3,3,3,5,6,7];
  console.log(filterSame(a)) //结果 [1,2,3,5,6,7]
```    

### 4. var foo  ={n: 1 } ;  var  bar  = foo ;  foo.x  = foo={n:  2 }  问foo.x?
  [链接:]  https://segmentfault.com/a/1190000002965140

```js
  * 考两个知识点: 一是 " . " 级别高于赋值表达式 "="; 二是 引用指向问题
      foo.x = foo = {n:2} 执行过程:
  01 foo.x 执行赋值, 等价于 bar.x(因为都是同一内存地址)
              |
              `--------foo.x = {n:1, x: undefined};

  02  foo ={ n: 2}, foo 变成一个新对象
             |
             `-------- 内存地址也变了
  03  foo.x =foo
             |
             `---------此时,foo.x 只能看做是 内存地址赋值 = {n:2}, 等价于bar.x ={n:2};
  04  因为foo 在02 过程是一个新对象, foo里面已没有了.x属性, 所以结果是 foo.x = undefined           

```

### 5. var  b  = 10  +  “20”   问b结果
  * 考知识点:  隐式转换, 变成字符串拼接
  * 结果: "1020"


### 6. ajax是什么，谈谈你对他理解
  * ajax 是一种 向服务器发送异步请求, 页面局部刷新技术
  * ajax原理:
    1 创建一个XMLHttpRequest对象
    2 发送一个http请求,调用open方法.包括,get ,post请求方式,url ;
    3 调用send方法发送数据.
    4 接收服务器发送回来数据,并进行js进行DOM操作
  * ajax 优点:
    1 向服务器发送异步请求, 用户无需等待可以继续其他操作, 提高了用户体验
    2 页面局部刷新数据, 按需取数据, 减少了不必要的数据传输,时间和降低网络上数据流量
    3 前后端更加负载平衡. AJAX的原则是“按需取数据”，可以最大程度的减少冗余请求和响应对服务器造成的负担，提升站点性能.
    4 基于标准被广泛支持
  * ajax缺点:
    1 ajax 干掉了Back和History功能, 没有历史记录
    2 增加了客户端的复杂度


### 7. 实现页面性能优化方法
  ![优化图片](./youhua.jpg)   
  [一枚链接:]http://tgideas.qq.com/webplat/info/news_version3/804/808/811/m579/201412/293834.shtml

### 8. 什么是响应式设计，响应式方式实现基本原理是什么
  * 响应式设计: 页面的设计与开发根据不同的设备(包括大小, 分辨率, 方向)而进行调整
  * 实现原理: css3 @media 媒体查询

### 9.  ”==”和“===”的区别
  "==" : 是值相等
  "===": 值相等,数据类型也相等


### 10.  你常用框架有哪些，好处是？在那些场合用？


### 11.  Doctype? 严格模式与混杂模式-如何触发这两种模式，区分它们有何意义?移动端怎么写doctype
  ```
  !DOCTYPE声明位于位于HTML文档中的第一行，处于html标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。

  标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。
  ```
  [触发模式:] https://www.cnblogs.com/gavinzzh-firstday/p/5723708.html

### 12. 请描述一下 cookies，sessionStorage 和 localStorage 的区别？
    cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。
    cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递。
    sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。

    存储大小：
      cookie数据大小不能超过4k。
      sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

    有期时间：
      localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
      sessionStorage  数据在当前浏览器窗口关闭后自动删除。
      cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭


### 13. 如何让div居中？div实现垂直水平居中? 浮动元素居中？绝对定位如何居中，实现圆点点击区域？代码实现
```css
    水平居中：给div设置一个宽度，然后添加margin:0 auto属性

    div{
      width:200px;
      margin:0 auto;
    }
    让绝对定位的div居中

    div {
      position: absolute;
      width: 300px;
      height: 300px;
      margin: auto;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      background-color: pink; /* 方便看效果 */
    }
    水平垂直居中一

    确定容器的宽高 宽500 高 300 的层
    设置层的外边距

    div {
      position: relative;     /* 相对定位或绝对定位均可 */
      width:500px;
      height:300px;
      top: 50%;
      left: 50%;
      margin: -150px 0 0 -250px;      /* 外边距为自身宽高的一半 */
      background-color: pink;     /* 方便看效果 */

    }
    水平垂直居中二

    未知容器的宽高，利用 `transform` 属性

    div {
      position: absolute;     /* 相对定位或绝对定位均可 */
      width:500px;
      height:300px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: pink;     /* 方便看效果 */

    }
    水平垂直居中三

    利用 flex 布局
    实际使用时应考虑兼容性

    .container {
      display: flex;
      align-items: center;        /* 垂直居中 */
      justify-content: center;    /* 水平居中 */

    }
    .container div {
      width: 100px;
      height: 100px;
      background-color: pink;     /* 方便看效果 */
    }  
```


### 14. 行内元素有哪些?块级元素有哪些?CSS的盒模型?伪类？
  1）行内元素有：a b span img input select strong（强调的语气）
  2）块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p
  3）常见的空元素：
  <br> <hr> <img> <input> <link> <meta>

### 15. CSS清除浮动的几种方法
  ```
  1. 直接给父盒子设置一个高度(严格的说不算清除浮动)。这种方式简单方便，但 是当父盒子没有办法直接设置高度就必须用其他方法清除浮动。
  ```

  ```
  2. 在发生浮动的父盒子中的最后添加一个空元素，然后给该空元素设置clear属性值。

    clear属性值    含义
    left    清除左浮动
    right    清除右浮动
    both    清除所有浮动
    但是当页面中发生浮动的元素很多时就需要添加很多空元素，不推荐使用。
  ```

  ```
  3. 直接给父盒子设置overflow属性
  overflow：hidden;
  这种方式简单方便，但是如果页面一旦出现了定位，那么定位可能会受到影响。

  overflow应用：

  overflow值    含义
  hidden    超出部分隐藏
  scroll    超出部分显示滚动条
  auto    超过部分显示滚动条，否则不显示
  ```

  ```
  4.使用伪元素清除浮动(不理解先背下来会用)
  css .clearfix::after, .clearfix::before { content: ""; height: 0; display: block; visibility: hidden; line-height: 0; clear: both; } .clearfix { zoom: 1;//兼容ie } 可以查看新浪等网站查看
  ```


### 16. px和em的区别  
    px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。 浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1 em=16 px。那么12px=0.75 em, 10 px=0.625 em

### 17. 怎样添加、移除、移动、复制、创建和查找节点?
 1）创建新节点 createDocumentFragment() //创建一个DOM片段
  createElement() //创建一个具体的元素
  createTextNode() //创建一个文本节点
 2）添加、移除、替换、插入  
  appendChild() //添加  
  removeChild() //移除
   replaceChild() //替换
    insertBefore() //插入
 3）查找 getElementsByTagName() //通过标签名称
  getElementsByName() //通过元素的Name属性的值
   getElementById() //通过元素Id，唯一性

### 18. 什么是SAP单页面应用，SAP单页面怎么优化搜索引擎优化
    [链接:] http://blog.csdn.net/zhangdaiscott/article/details/51004301  
    [链接:] http://ziyuan.baidu.com/college/articleinfo?id=294
     * 单页 Web 应用 (single-page application 简称为 SPA) 是一种特殊的 Web 应用。它将所有的活动局限于一个Web页面中，仅在该Web页面初始化时加载相应的HTML、JavaScript 和 CSS。一旦页面加载完成了，SPA不会因为用户的操作而进行页面的重新加载或跳转。取而代之的是利用 JavaScript 动态的变换HTML的内容，从而实现UI与用户的交互。由于避免了页面的重新加载，SPA 可以提供较为流畅的用户体验。
    *

### 19. 数组方法pop() push() unshift() shift()
    * pop(): 删除数组中最后一个元素;  push(): 添加一个元素到数组最后部分 ; unshift():添加一个元素到数组起始位置  shift(): 删除数组第一个元素

### 20. window.onload和document.ready区别
    * window.onload 所有标签加载完,和资源比如图片,视频加载完才执行.  document.load 标签加载完就运行
    * window.onload 只可以运行一次, document.ready 可以运行多次


### 21. html5调用了哪个文件用于缓存
```
  在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
  原理：HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。


  如何使用：
  1、页面头部像下面一样加入一个manifest的属性；
  2、在cache.manifest文件的编写离线存储的资源；
    CACHE MANIFEST
    #v0.11
    CACHE:
    js/app.js
    css/style.css
    NETWORK:
    resourse/logo.png
    FALLBACK:
    / /offline.html
  ```
3、在离线状态时，操作window.applicationCache进行需求实现。
### 22. http状态码
    * 1** 代表请求已经被接收；
    * 2** 代表请求已成功被服务器接收、理解、并接受。常用的200表示请求已成功，请求所希望的响应头或数据体将随此响应返回；
    * 3** 代表重定向。
    * 4** 代表客户端错误。404 表示网页不存在。
    * 5** 代表服务器错误。500 表示服务器内部错误，503 表示服务器暂时不可用

### 23. jquery多级联动


### 24. 懒动加载方式加载图片，懒动加载是什么？
    * 懒加载也叫延迟加载：JS图片延迟加载 延迟加载图片或符合某些条件时才加载某些图片.
    * 意义： 懒加载的主要目的是作为服务器前端的优化，减少请求数或延迟请求.
    * 实现方式  
      .第一种是纯粹的延迟加载，使用setTimeOut或setInterval进行加载延迟.  
      .第二种是条件加载，符合某些条件，或触发了某些事件才开始异步下载。
      .第三种是可视区加载，即仅加载用户可以看到的区域，这个主要由监控滚动条来实现，一般会在距用户看到某图片前一定距离遍开始加载，这样能保证用户拉下时正好能看到图片。
      [链接:] https://www.2cto.com/kf/201401/273784.html

### 25. px和em的区别
     *   px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。 浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em  
### 26. javascript使用正则方法实现清除字符串前后的空格方法, 还有正则表达式验证邮箱格式
    ```js  
    function trim(str) {
       if (typeof str === "string") {
         return str.replace(/(^\s*)|(\s*)$/g,"");
         }
       }

    let a = " 12345   ";
    console.log(trim(a).length);

    ```  
    ```js  
    var reg = /^(\w)+(\.\w+)*@(\w)+((\.\w{2,3}){1,3})$/;    var email = "example@qq.com";
    console.log(reg.test(email));//true

    ```
### 27. 对前端工程师这个职位你是怎么样理解的？
    前端是最贴近用户的程序员，比后端、数据库、产品经理、运营、安全都近。
    1、实现界面交互
    2、提升用户体验
    3、有了Node.js，前端可以实现服务端的一些事情


    前端是最贴近用户的程序员，前端的能力就是能让产品从 90分进化到 100 分，甚至更好，

    参与项目，快速高质量完成实现效果图，精确到1px；

    与团队成员，UI设计，产品经理的沟通；

    做好的页面结构，页面重构和用户体验；

    处理hack，兼容、写出优美的代码格式；

    针对服务器的优化、拥抱最新前端技术。

### 28.你的能力现在能做什么? 你的职业发展方向?

### 29.你在工作中遇到最大难事是什么？解决办法？
