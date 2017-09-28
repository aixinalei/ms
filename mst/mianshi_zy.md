# App打包
```
答案：http://jingyan.baidu.com/article/c45ad29c2ffc1e051653e272.html
```
# js基本数据类型
```
String Number Boolean Object Array Undefined Function Null
```
# 什么是闭包
```
有权访问另一个函数内部作用域的变量的函数叫闭包
```
# 闭包的作用
```
减少全局变量，使变量私有化！
```
# 字符串的常用方法
```
例如：					
var str = "ABC";
str.charCodeAt(0);
结果：65
将字符串转成ascii码
String.fromCharCode(65,66,112);
结果：ABp
将ascii码转成字符串
str.charAt(1);
获取字符
012345
var str = "ABCDEF";
str.slice(2,4);
结果：CD
截取字符串起始位置到结束位置
012345
var str = "ABCDEF";
str.substr(2,4);
结果：CDEF
截取字符串起始位置到截取的几位
var str = "ABCDEF";
str.concat("ABCDEF","ABC");
结果：ABCDEFABCDEFABC
连接字符串
var str = "AA BB CC DD EE FF";
alert(str.split(" "，3));
结果：
AA,BB,CC
截取字符串
var str = "ABCabc";
str.toLowerCase();
结果：abcabc
将字母转换成小写
var str = "ABCabc";
str.toUpperCase();
结果：ABCABC
将字符转换成大写
```
# 数组的常用方法
```
push：向数组的末尾增加一项 返回值是数组的新长度
unshift：向数组开头增加一项 返回值是数组的新长度
pop:删除数组的末尾项 返回值是删除的数组项
shift:删除数组开头项 返回被删除的开头项目
splice：删除数组中的任意项 返回值是被删除的数组项
slice:复制数组 返回值是复制到的新数组 写上数值之后 不包含被复制的最后一项

拼接：
concat:把一个数组和另一个数组拼接在一起 返回拼接好的数组
join:把数组中的每一项 按照指定的分隔符拼接成字符串

排序：
reverse:倒序数组 返回值倒序数组 原有数组改变
sort:根据匿名函数进行冒泡排序 b-a倒序 a-b升序

indexOf:返回获取项在数组中的索引
lastIndexOf:返回获取项在数组中出现的最后一次索引
forEach: 循环遍历数组 参数是一个匿名函数 默认返回为undefined
map：循环遍历数组 参数是一个匿名函数
```
# js类的使用
```
/***定义类***/
var Class = function(){
  var _self = this;//把本身引用负值到一变量上
  var _Field = "Test Field"; //私有字段
  var privateMethod = function(){ //私有方法
    alert(_self.Property); //调用属性
  }
  this.Property = "Test Property"; //公有属性
  this.Method = function(){ //公有方法
    alert(_Field); //调用私用字段
    privateMethod(); //调用私用方法
  }


实例化类
var c = new Class();
c.Method(); //使用方法
```
# 原型链
```
JavaScrip可以采用构造器(constructor)生成一个新的对象,每个构造器都拥有一个prototype属性,而每个通过此构造器生成的对象都有一个指向该构造器原型(prototype)的内部私有的链接(proto),而这个prototype因为是个对象,它也拥有自己的原型,这么一级一级直到原型为null,这就构成了原型链
```
# Object原型指向谁
```
每个构造函数内部均有一个prototype原型指针，指向该类型的原型对象C.prototype。原型对象C.prototype中包含一个回指向构造函数的指针constructor。这样就实现了构造函数和原型对象间的双向绑定。每个实例对象内部也包含一个指向原型对象C.prototype的指针。
```
# typeof
```
typeof返回变量的类型
```
# DOM是什么
```
HTML DOM 定义了所有 HTML 元素的对象和属性，以及访问它们的方法。
换言之，HTML DOM 是关于如何获取、修改、添加或删除 HTML 元素的标准
```
# JQuery常用的方法
```
http://www.css88.com/jqapi-1.9/
```

# JQuery中的find方法是干嘛的

```
方法获得当前元素集合中每个元素的后代、通过选择器、jQuery 对象或元素来筛选
```
# 事件冒泡
```
当你使用事件冒泡时，子级元素先触发，父级元素后触发
```
# 事件捕获
```
当你使用事件捕获时，父级元素先触发，子级元素后触发
```
# CSS3
```

移动 translate3d(value,value,value) 可以改变元素的位置.
缩放 scale3d(x, y, z), scaleX(x) .
旋转 rotate3d(x,y,z,deg), rotateX(deg) 可以对元素进行旋转.
倾斜 skew(deg, deg),skewX(deg) ,skewY(deg)可以使元素按一定的角度进行倾斜
以上四个还有2D
------------------------------------------------------------------
border-radius 边框圆角化
rotate（angle）  定义 2D 旋转
text-shadow  阴影 可分别设置偏移量、模糊度、颜色（可设透明度）
background: linear-gradient(to bottom , red, white); 线性渐变
background-image: radial-gradient(100px at center,yellow 50%  , blue, red); 径向渐变
transition-property 设置过渡属性
transition-duration 设置过渡时间
transition-timing-function 设置过渡速度
transition-delay 设置过渡延时】

animation-name 设置动画序列名称
animation-duration 动画持续时间
animation-delay 动画延时时间
animation-timing-function 动画执行速度，linear、ease等
animation-play-state 动画播放状态，play、paused等
animation-direction 动画逆播，alternate等
animation-fill-mode 动画执行完毕后状态，forwards、backwards等
animation-iteration-count 动画执行次数，inifinate等

flex-grow 设置的flex子项的扩展比例
flex-shrink 设置的flex子项的收缩比例
flex-basis 设置的flex子项的基准宽度
flex-flow 设置flex-direction 和flex-wrap
flex-direction 设置子元素排列的方向
flex-wrap 设置子元素是否允许换行
justify-content 横轴的对齐方式
align-items 纵轴对齐
align-content 设置的横向有换行的盒子的纵轴对齐
align-self 子元素自身的纵轴对齐
order 设置子元素的排列顺序
```

# canvas (绘画)

```
https://nts.newbieol.com/classroom/study/327?lid=4238
```
# 如何实现Socket.io
```
socket.io 的核心就是这两个函数了，通过 emit 和 on 可以轻松地实现服务器与客户端之间的双向通信
emit ：用来发射一个事件或者说触发一个事件，第一个参数为事件名，第二个参数为要发送的数据，第三个参数为回调函数（一般省略，如需对方接受到信息后立即得到确认时，则需要用到回调函数）。
on ：用来监听一个 emit 发射的事件，第一个参数为要监听的事件名，第二个参数为一个匿名函数用来接收对方发来的数据，该匿名函数的第一个参数为接收的数据，若有第二个参数，则为要返回的函数
connect 事件，当收到对方发来的数据后触发 message 事件（通常为 socket.send() 触发），当对方关闭连接后触发 disconnect 事件
```

# Ajax和jsonp干什么用的，有什么区别？

```
1.ajax和jsonp的调用方式很像，目的一样，都是请求url，然后把服务器返回的数据进行处理，因此jquery和ext等框架都把jsonp作为ajax的一种形式进行了封装；
2.实质不同
　　　ajax的核心是通过xmlHttpRequest获取非本页内容
　　　jsonp的核心是动态添加script标签调用服务器提供的js脚本
3.区别联系
　　 不在于是否跨域
　　 ajax通过服务端代理一样跨域
　　 jsonp也不并不排斥同域的数据的获取
4.jsonp是一种方式或者说非强制性的协议
    ajax也不一定非要用json格式来传递数据
```

# 对jquery的ajax进行二次封装
```

** ajax封装 **
封装时用到的参数：

url 发送请求的地址
data 发送到服务器的数据，数组存储，如：{"username": "张三", "password": 123456}
succCallback 成功回调函数
errorCallback 失败回调函数
type 请求方式("POST" 或 "GET")， 默认已经设置为 "POST"
dataType 预期服务器返回的数据类型，常用的如：xml、html、json、text
reference jquery-1.7.1.js

        function $ajax(url, postData, succCallback, errorCallback, type, dataType){
            var type = type || "post";
            var dataType = dataType || "json";

            $.ajax({
                type: type,
                url: url,
                data: postData,
                dataType: dataType,

                beforeSend: function(){  //开始loading
                    $(".js_loading").show();                    
                },

                success: function(res){
                    if(res.success){
                        if(succCallback){
                            succCallback(res);
                        }                       
                    }else{
                        if(errorCallback){
                            errorCallback(res);
                        }
                    }                   
                },

                complete: function(){   //结束loading
                    //$(".js_loading").remove();
                    $(".js_loading").hide();
                }
            });
        }
    });

```
# 怎么实现分页

```
1.首先在页面放两个隐藏域，一个是当前页码，一个是总页码，总页码是页面加载完，从后台查询出来后直接附上值的，当前页码是每操作一个，就要对当前页码赋值
2.写一个页面加载完的function，给总页码和当前页码赋值
3.抽取的ajax方法，此页面会用到好几次这个方法，所有把它收取了出来，因为页面的数据时通过ajax从后台获取到的，后台返回的是一个List集合
```

# 公司总共js脚本总共在多少行代码？
```
在5000  ~  8000 行左右
```

# js脚本是每个页面多写一个吗？

```
可以每一个页面写一个js脚本。也可以写一个JS脚本文件直接引用。
```

# call 方法和apply方法的区别?

```
共同功能：绑定this值
区别：apply和call的功能是一样的，只是传入的参数列表形式不同。
apply ：可以接收数组，返回的结果是将数组进行拆分
call : 可以接收多个单个参数
```

