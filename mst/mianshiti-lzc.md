## 自我介绍(略)

## 1.react的原理
~~~
自己复习
~~~

## 2.react的生命周期
1. Mounting: 已插入真实DOM  
1. Updating: 正在被重新渲染  
1. Unmounting: 已移出真实的DOM  

 1. componentWillMount(): 在渲染前调用, 在客户端也在服务端.
 1. componentDidMount(): 在第一次渲染后调用，只在客户端。之后组件已经生成了对应的DOM结构，可以通过this.getDOMNode()来进行访问。 如果你想和其他JavaScript框架一起使用，可以在这个方法中调用setTimeout, setInterval或者发送AJAX请求等操作(防止异部操作阻塞UI)。
 1. componentWillUpdate(object nextProps, object nextState): 在组件接收到一个新的prop时被调用。这个方法在初始化render时不会被调用。
 1. componentDidUpdate(object nextProps, object nextState): 返回一个布尔值。在组件接收到新的props或者state时被调用。在初始化时或者使用forceUpdate时不被调用。
 1. componentWileUnmount(): 在组件从 DOM 中移除的时候立刻被调用。

## 3.redux的原理
~~~
事件触发  ->  action(对象)  ->  dispath(action)  ->  store  ->  reducer(state,action)  ->  new state  ->  render()
~~~

## 4.为什么要用redux
~~~
当react变得复杂，能更好的管理state和简化组件间的数据传递
~~~

## 面试心得
```
理论知识只是基础，回答不到重点，感觉面试官需要你回答的是你对这技术的理解、用了这技术后发现的问题、使用经验等更上一层的回答，看来我还是太年轻了！！！！！！
```
