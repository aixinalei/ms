### 1. label的作用是什么?是怎么用的?
        label是说明标签,他的for的值和表单字段id值相同会显示关联起来.

### 2. title与h1的区别、b与strong的区别、i与em的区别？
        title属性没有明确标题,h1则表示层次分明的标题.
        strong是标明重点内容,有语义加强的含义. b标明重要内容
        em表示强调的文本,i展示斜体
### 3.  如何让div居中？div实现垂直水平居中? 浮动元素居中？绝对定位如何居中?
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
### 4. position的值relative和absolute相对于原点?
    relative: 相对于元素本身, padding左上角;
    absolute: 相对最近已定位祖先元素或者是body元素的padding左上角
### 6. absolute的containing block(容器块)计算方式跟正常流有什么关系?

### 10. 写一个通用的事件侦听器函数?
```js
          var Event = {
          //得到事件对象
              events: function(e) {
                e = e | window.event;
                return e;
              },
         // 添加事件
              addEvent: function(obj, eventname,handle) {
                if(obj.addEventListener) {
                  return obj.addEventListener(eventname, handle,false);
                }
                else if(obj.attachEvent) {
                  return obj.attachEvent("on"+eventname, handle);
                }
                else{
                  return  obj["on"+eventname] = handle;
                }
              }

         // 移除事件
            removeEvent: function(obj, eventname, handle) {
              if(obj.removeEventListener) {
                return obj.removeEventListener(eventname, handle, false);
              }
              else if(obj.detachEvent) {
                return obj.detachEvent("on"+eventname,handle);
              }
              else{
                return obj["on"+eventname] = handle;
              }
            }

        // 阻止事件默认行为
        preventDefault: function(e) {
          if(e.preventDefault) {
            return e.preventDefault();
          }
          else{
            e.returnValue = false;
          }
        }
        //阻止冒泡
        stopPropagation: function(e) {
          if(e.stopPropagation) {
            return e.stopPropagation();
          }
          else {
            return e.cancelBubble = true;
          }
        }  
        //得到事件源头元素
        eventTarget: function(e) {
          if(e.target) {
            return e.target
          }
          else {
            return e.srcElement;
          }
        }
          }
```

### 15. 模块化开发是怎么做的?


### 19. 用js实现千位分隔符?(提示:正则 + replace)?

### 20. Object.is() 和原来的比较操作符 "===" 和"=="有什么区别?  

### 21. 创建原生的方法, 给字符串对象定义一个repeatify功能, 当传入一个整数n 时,他会返回一个重复n次字符串的结果.例如: console.log("hello".repeatify(3));应打印 hellohellohello.  

### 22. 下面一段代码的输出结果是?
   ```js
      for(var i =0; i<5; i++) {
        setTimeout(function() {
          console.log(new Date, i);
        },1000);
      }
      console.log(new Date, i);
   ```
### 24. 实现一个函数clone, 可以对javascript的5种数据类型进行值复制.


### 25. 继承的使用, 请用编码实现几种继承方式

### 26. 试用编码的方式实现一个数据双向调用  

### 27. 下面有一个调用模板字符串,生成正式模板的实例,怎么编译这个模板字符串呢?请用末班字符串的编码方式实现?
