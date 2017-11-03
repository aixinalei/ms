 # h2 面试
 ## 内容
 ### 1.  js数据类型
    * 简单类型: String, Number, Boolean, Undefined
    * 引用类型: Function Object

 ### 2. 简单类型和引用类型比较
    * 简单类型数据存放在栈内存中, 引用类型数据存在在堆内存中


 ### 3. 函数对象跟原生对象有哪些不一样地方,或者说少了什么东西?   
 ```js
    //函数对象通过new Funtion() 构造出来, 原生对象是通过new Object()构造出来.
    const fn = new Function();
    const obj = new Object();
    console.log(fn);
    console.log(obj);  
```
 ### 4. 函数对象有什么属性和方法?


 ### 5. 怎么判断一个引用是不是一个数组?
    *  用Array.isArray() 判断, 返回真为数组.
    *  var b = [1,2];
       console.log((b.constructor == Array)); // 输出为true

 ### 6. instanceof 判断原理

    *  instanceof表示的就是一种继承关系.
    *  Instanceof运算符的第一个变量是一个对象，暂时称为A；第二个变量一般是一个函数，暂时称为B
    * 沿着A的__proto__这条线来找，同时沿着B的prototype这条线来找，如果两条线能找到同一个引用，即同一个对象，那么就返回true。如果找到终点还未重合，则返回false。

 ### 7. ES6 相对于 ES5 多出了什么内容?
    * Block-Scoped Constructs Let and Const（块作用域构造Let and Const）
    * Arrow Functions （箭头函数）in ES6
    * Template Literals （模板文本）in ES6
    * Multi-line Strings （多行字符串）in ES6
    * Classes（类） in ES6
    * Destructuring Assignment （解构赋值）in ES6
    * Default Parameters（默认参数） in ES6
    * Enhanced Object Literals （增强的对象文本）in ES6
    * Promises in ES6
    * Modules（模块） in ES6

 ### 8. 箭头函数特点(为什么用箭头函数?少写funtion外多出了什么特性?)
    1.箭头函数的语法写法很简单
    2.对 this 的关联。函数内置 this 的值，取决于箭头函数在哪儿定义，而非箭头函数执行的上下文环境。
    3.new 不可用。箭头函数不能使用 new 关键字来实例化对象，不然会报错。
    4.this 不可变。函数内置 this 不可变，在函数体内整个执行环境中为常量。
    5.没有arguments对象。更不能通过arguments对象访问传入参数。只能使用显式命名或其他ES6新特性来完成。

 ### 9. 不用api,自己实现浅拷贝

```js
const obj1 = {
  "name":"lisi",
   "age": 22,
 "arr": [1,2,3]};

 function lowerCopy(obj) {
    const ob = {};
    for(var elem in obj ){
      if(obj.hasOwnProperty(elem)) {
        ob[elem] = obj[elem];
      }
    }
    return ob;
 };

 var obj2 = lowerCopy(obj1);
```
 ### 10. 浅拷贝和深拷贝实现各自思路
    1.都利用遍历方法.
    浅拷贝只是简单复制就行.
    深拷贝除了遍历外,还要每一次遍历先判断是不是Object类型,"如果是,则采用递归拷贝一次,重复这样的操作.如果不是,则简单复制", 一直到遍历完.
    [详细可以看链接:]http://www.cnblogs.com/Chen-XiaoJun/p/6217373.html

 ### 11. 原生实现深拷贝
  ```js
  1 递归实现深拷贝

  function deepCopy (initObj, endObj) {
  const obj = endObj || {};

  for(let i in initObj) {
    var prop = initalObj[i]; // 避免相互引用对象导致死循环，如initalObj.a = initalObj的情况
    if(prop === obj) {            
      continue;
    }     

    if(typeof initObj[i] == 'object') {
      obj[i] = (initObj[i].constructor === Array) ? [] : {};
      arguments.callee(initObj[i], obj[i]); //包含当前执行函数,用于递归调用
    }
    else {
      obj[i] = initObj[i];
    }
  }
  return obj;
}

var a = {};
var obj1 = {"name": "lisi", "age": 1, "arr": [1, 2, 3]};
var obj2 = deepCopy(obj1, a);
obj2.arr = [3, 4,5];
console.log(obj1);  //对象obj2.arr改变数据,但obj1.arr=[1,2,3] ,说明深拷贝成功

  ```

 ### 12. http包熟悉情况, 头部有什么字段
   [详细可以看链接:] http://www.jianshu.com/p/6e86903d74f7  

   1.常用Request请求头字段:  

    Accept 设置接受内容的类型:
  * Accept: text/plain;

    Accept-Charset 设置接受的字符编码:
  * Accept-Charset: utf-8

   Accept-Encoding 设置接受的编码格式:
  * Accept-Encoding: gzip, deflate

   Accept-Language 设置接受的语言:
  * Accept-Language: zh-CN,zh;q=0.8

  Authorization 设置HTTP身份验证的凭证:
  * Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==

  Content-Type 设置请求体的MIME类型:
  * Content-Type: application/x-www-form-urlencoded

  Upgrade-Insecure-Requests 标识服务器是否可以处理HTTPS协议:
  *  Upgrade-Insecure-Requests: 1

  User-Agent 用户代理的字符串值:
  * User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:12.0) Gecko/20100101 Firefox/21.0

  Referer 设置前一个页面的地址，并且前一个页面中的连接指向当前请求，意思就是如果当前请求是在A页面中发送的，那么referer就是A页面的url地址:
  * Referer: http://en.wikipedia.org/wiki/Main_Page

  Cookie 设置服务器使用Set-Cookie发送的http cookie:
  *  Cookie: $Version=1; Skin=new;


  2.响应Response 头部:
  Connection 设置当前连接和hop-by-hop协议请求字段列表的控制选项:
  * Connection: keep-alive

  Content-Encoding 设置数据使用的编码类型:
  * Content-Encoding: gzip

  Content-Type 设置响应体的MIME类型:
  * Content-Type: text/html; charset=utf-8

  Date 设置消息发送的日期和时间:
  * Date: Tue, 15 Nov 1994 08:12:31 GMT

  Server 服务器名称:
  * Server: Apache/2.4.1 (Unix)

  Vary 通知下级代理如何匹配未来的请求头已让其决定缓存的响应是否可用而不是重新从源主机请求新的:
  * Vary: accept-encoding


 ### 13. get 和 post 自定义头部
 [链接:] http://blog.csdn.net/javandroid/article/details/29884033
 以用google搜索domety为例，Request格式如下:   
 [简书:] http://www.jianshu.com/p/6e86903d74f7
 ```js
   GET /search?hl=zh-CN&source=hp&q=domety&aq=f&oq= HTTP/1.1    
  Accept: image/gif, image/x-xbitmap, image/jpeg, image/pjpeg, application/vnd.ms-excel, application/vnd.ms-powerpoint,   
  application/msword, application/x-silverlight, application/x-shockwave-flash, */*    
  Referer: <a href="http://www.google.cn/">http://www.google.cn/</a>    
  Accept-Language: zh-cn    
  Accept-Encoding: gzip, deflate    
  User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1; SV1; .NET CLR 2.0.50727; TheWorld)    
  Host: <a href="http://www.google.cn">www.google.cn</a>    
  Connection: Keep-Alive    
  Cookie: PREF=ID=80a06da87be9ae3c:U=f7167333e2c3b714:NW=1:TM=1261551909:LM=1261551917:S=ybYcq2wpfefs4V9g;   
  NID=31=ojj8d-IygaEtSxLgaJmqSjVhCspkviJrB6omjamNrSm8lZhKy_yMfO2M4QMRKcH1g0iQv9u-2hfBW7bUFwVh7pGaRUb0RnHcJU37y-  
  FxlRugatx63JLv7CWMD6UB_O_r   

  ```

  ```js
    POST /search HTTP/1.1    
  Accept: image/gif, image/x-xbitmap, image/jpeg, image/pjpeg, application/vnd.ms-excel, application/vnd.ms-powerpoint,   
  application/msword, application/x-silverlight, application/x-shockwave-flash, */*    
  Referer: <a href="http://www.google.cn/">http://www.google.cn/</a>    
  Accept-Language: zh-cn    
  Accept-Encoding: gzip, deflate    
  User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1; SV1; .NET CLR 2.0.50727; TheWorld)    
  Host: <a href="http://www.google.cn">www.google.cn</a>    
  Connection: Keep-Alive    
  Cookie: PREF=ID=80a06da87be9ae3c:U=f7167333e2c3b714:NW=1:TM=1261551909:LM=1261551917:S=ybYcq2wpfefs4V9g;   
  NID=31=ojj8d-IygaEtSxLgaJmqSjVhCspkviJrB6omjamNrSm8lZhKy_yMfO2M4QMRKcH1g0iQv9u-2hfBW7bUFwVh7pGaRUb0RnHcJU37y-  
  FxlRugatx63JLv7CWMD6UB_O_r    

  hl=zh-CN&source=hp&q=domety  
  ```

 ### 14. 跨域, ajax交互时, http头部有什么特殊字段?
 [链接:] http://blog.csdn.net/hu_feng903/article/details/70227953
  ```
  服务端设置响应头
  header('Access-Control-Allow-Origin:*');  //支持全域名访问，不安全，部署后需要固定限制为客户端网址
  header('Access-Control-Allow-Methods:POST,GET,OPTIONS,DELETE'); //支持的http 动作
  header('Access-Control-Allow-Headers:x-requested-with,content-type');  //响应头 请按照自己需求添加。
  ```

 ### 15. React 生命周期有哪些?(按组件加载顺序)
 ```
 01 Mounting
         |
         `----getInitialState, componentWillMount, mounting, componentDidMount
 02 Updating
         |
         `----componentReceiveProps,shouldComponentUpdate, componentWillUpdate, Updating, componentDidUpate
 03 Unumounting
         |
         `----componentWillUnmount, Unmount

 ```
 ### 16. 如果有异步,你会把它放到哪个生命周期部分让它执行?(或者说把它放在ComponentDidMount和ComponentWillMount区别)
        * 把异步请求如 ajax 放在 ComponentDidMount函数里面

 ### 17. setState对api了解
        * this.setState(xxx) 修改时异步的操作，不一定会立刻更新
        * react会将 多个setState进行合并，分批处理，因此多个setState可能只更新一次
        * this.setState是浅合并修改

 ### 18. setState实现和特性
        * 和17题是同一个问题

 ### 19. 初始化一个count = 1, 在后面触发一个事件调用handleChange方法, 这个方法连续执行3次setState, 问最后输出count结果
  ```js
 getInitialState: function(){
                    return {count: 1 };
                },
                handleChange: function(event){
                    this.setState({count: count +1});
                    this.setState({count: count +1});
                    this.setState({count: count +1});
                },
  ```
        * 结果是: count = 2;

 ### 20. 上面结果为count = 1 的原因 , 为什么setState只渲染了一次
        * 答案在第17题

 ### 21. 同时使用 React 和bootstrap, 你是怎么结合的?
        * 使用React-bootstrap

 ### 22. 在React 使用的ui有哪些? Sementic 是基于什么做的?
        * React-Bootstrap , Material-UI , React Desktop , Semantic-UI-React ,  Ant-design , Blueprint ....
        [链接:] http://www.iteye.com/news/32408

 ### 23. 移动端性能优化有哪些

 ![优化图片](./youhua.jpg)   
 [一枚链接:]http://tgideas.qq.com/webplat/info/news_version3/804/808/811/m579/201412/293834.shtml

 ### 24. 单从打包角度来说,过程有哪些来提升文件效率(或者说打包过程中,配置文件,有什么作用)
        * 去除不必要的插件
        * 提取第三方库
        * 代码压缩
        * 代码分割
        * 设置缓存
        [链接:] http://www.jianshu.com/p/a64735eb0e2b
        
 ### 25. node.js怎么删除一个文件?
 ```js
  1 删除文件:
    var fs = require('fs');
    fs.unlink(filepath,callback);
  2 删除文件夹
  var fs = require('fs');
 fs.rmdir(dirname, callback);
  ```

 ### 26. mongodb 数据库缓存有没有涉猎?(有没有什么接口缓存)  
 [链接:] http://www.cnblogs.com/Fredric-2013/p/4520134.html  

      参考了mongoose-redis-cache这个插件, 初始化一个redis客户端，然后重写mongoose的exec方法，将exec的参数设置为redis的key，将数据库返回的结果设置为对应的value。

 ### 27. 写css 时, 有什么要注意的(在项目有大量css代码时这种情况)
 [链接]http://www.jianshu.com/p/e44ff354933f  
 会注意对css代码进行重构:

  提高CSS性能：
    * 尽量将样式写在单独的css文件里面，在head元素中引用
    * 不使用@import
    * 避免使用复杂的选择器，层级越少越好
    * 精简页面的样式文件，去掉不用的样式
    * 利用CSS继承减少代码量

   提高可维护性：
    * 良好命名和备注
    * 提取重复样式

 ### 28. 在渲染过程中, 一个标签嵌套多个标签,多了会出现什么结果(比如: 一个标签嵌套2个标签, 另一个标签嵌套3个标签)
 [链接:]http://lib.csdn.net/article/html5/48259    
 ```html
 <div>1 <div>2</div><div>3</div></div>   //先显示3，然后2， 最后1  
 ```
