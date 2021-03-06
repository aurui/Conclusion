# 踩坑心得



## Element-UI



#### MessageBox 组件自定义显示内容

有时候我们希望确认弹窗的提示内容可进一步自定义，比如显示一个列表，显示不同的颜色及字体大小等等。

这时候需要用到MessageBox.confirm方法，该方法有三个参数，分别是message,title和options，其中，message是必填的，但可以options中覆盖其内容，下面是代码演示：

```javascript
const h = this.$createElement
MessageBox.confirm('该信息不会被显示', {
  title: `归档确认`,
  message: h('div', {'class': 'confirm-con'}, [
    h('h4', {'class': 'tit'}, warning),
    h('div', {'class': 'msg'}, `确认归档这6位客户?`)
  ]),
  confirmButtonText: '确定',
  cancelButtonText: '取消'
})
```



#### Form 表单验证

1. 如果form绑定的数据为动态生成，那么rules（验证规则）必须在其之后声明；



#### 组件命名冲突

在工单详情中有个“工单进展”组件，随手命名为 `Progress` ，然后发现浏览器报了一个错误：`Do not use built-in or reserved HTML elements as component id: Progress`。原因是Element-UI中也有个 `Progress`组件，而这个组件是全局注册的，从而导致了组件命名冲突。

关于组件的命名规范，可以看一下这篇拓展阅读：[聊聊 Vue 组件命名那些事](http://cnodejs.org/topic/5816aabdcf18d0333412d323)



#### 引入组件路径，注意区分大小写

1. 如果路径中错写了大小写，具体表现为组建加载正常，但是修改组件内容不会触发更新；
2. Linux中严格区分大小写，如果项目中错写了大小写路径，发布到线上后会导致引用错误。



## Javascript





## Vuejs
  

## Vuex

#### 父子组件之间传参

  1.父子组件之间的传参如果是对象和数组，即使赋值给子组件的一个变量，如果不深度拷贝的话，子组件改变父组件也会改变，因为他们指向的是同一个地址。
    深度拷贝：JSON.parse(JSON.stringify())或者slice()
    
  2.父子组件之间的传参如果是对象和数组,最好采用工厂模式，因为工程模式的意思是当我调用这个函数，实际上是先利用类创建了一个对象，然后返回这个对象。
  () => {}
 
## Vue-router





