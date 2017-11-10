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

### 4. var foo  ={n: 1 }   var  bar  = foo   foo.x  = foo={n:  2 }  问foo.x?


### 5. var  b  = 10  +  “20”   问b结果


### 6. ajax是什么，谈谈你对他理解


### 7. 实现页面性能优化方法


### 8. 什么是响应式方式，响应式方式实现基本原理是什么

### 9.  ”==”和“===”的区别


### 10.  你常用框架有哪些，好处是？在那些场合用？


### 11.  Doctype? 严格模式与混杂模式-如何触发这两种模式，区分它们有何意义?移动端怎么写doctype


### 12. 请描述一下 cookies，sessionStorage 和 localStorage 的区别？


### 13. 如何让div居中？div实现垂直水平居中? 浮动元素居中？绝对定位如何居中，实现圆点点击区域？代码实现


### 14. 行内元素有哪些?块级元素有哪些?CSS的盒模型?伪类？

### 15. CSS清除浮动的几种方法

### 16. px和em的区别  
    px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。 浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em, 10px=0.625em

### 17. 怎样添加、移除、移动、复制、创建和查找节点？  
    1）创建新节点 createDocumentFragment() //创建一个DOM片段 createElement() //创建一个具体的元素 createTextNode() //创建一个文本节点2）添加、移除、替换、插入 appendChild() //添加 removeChild() //移除 replaceChild() //替换 insertBefore() //插入3）查找 getElementsByTagName() //通过标签名称 getElementsByName() //通过元素的Name属性的值 getElementById() //通过元素Id，唯一性

### 18. 什么是SAP单页面应用，SAP单页面怎么优化搜索引擎优化


### 19. 数组方法pop() push() unshift() shift()


### 20. window.onload和document.load区别


### 21. html5调用了哪个文件用于缓存

### 22. http状态码

### 23. jquery多级联动


### 24. 懒动加载方式加载图片，懒动加载是什么？

### 25. px和em的区别
    px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。 浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em
### 26. javascript使用正则方法实现清除字符串前后的空格方法, 还有正则表达式验证邮箱格式
    ```js
    ```js
      function trim(str) {    if (str &amp;&amp; typeof str === "string") {        return str.replace(/(^\s*)|(\s*)$/g,""); //去除前后空白符    }}
    ```  
    var reg = /^(\w)+(\.\w+)*@(\w)+((\.\w{2,3}){1,3})$/;    var email = "example@qq.com";    console.log(reg.test(email));  // true

    ```
### 27. 对前端工程师这个职位你是怎么样理解的？

### 28.你的能力现在能做什么? 你的职业发展方向?

### 29.你在工作中遇到最大难事是什么？解决办法？
