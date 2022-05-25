## VUE响应式数据的原理  
````js
Object.defineProperty定义data的属性
具体的过程：首先Vue使用 initData 初始化用户传入的参数，
然后使用  new Observer 对数据进行观测，如果数据是一个对象类型就会调用 this.walk（value） 对对象进行处理，
内部使用  defineeReactive  循环对象属性定义响应式变化，核心就是使用 Object.defineProperty 重新定义数据。
````

## MVVM
````js
全称： Model-View-ViewModel ， Model 表示数据模型层。 view 表示视图层， ViewModel 是 View 和 Model 层的桥梁，数据绑定到 viewModel 层并自动渲染到页面中，视图变化通知 viewModel 层更新数据。
````


## Vue的生命周期
````js
beforeCreate ：实例初始化之后，数据观测之前调用
created：实例创建万之后调用。实例完成：数据观测、属性和方法的运算、 watch/event 事件回调。无 $el .
beforeMount：在挂载之前调用，相关 render 函数首次被调用
mounted：了被新创建的vm.$el替换，并挂载到实例上去之后调用改钩子。
beforeUpdate：数据更新前调用，发生在虚拟DOM重新渲染和打补丁，在这之后会调用改钩子。
updated：由于数据更改导致的虚拟DOM重新渲染和打补丁，在这之后会调用改钩子。
beforeDestroy：实例销毁前调用，实例仍然可用。
destroyed：实例销毁之后调用，调用后，Vue实例指示的所有东西都会解绑，所有事件监听器和所有子实例都会被移除
````

## 组件通信
````js
父子间通信:父亲提供数据通过属性 props传给儿子；儿子通过 $on绑父亲的事件，再通过 $emit 触发自己的事件（发布订阅）利用父子关系 $parent 、 $children ，
获取父子组件实例的方法。
父组件提供数据，子组件注入。 provide 、 inject ，插件用得多。
ref 获取组件实例，调用组件的属性、方法跨组件通信 Event Bus  （Vue.prototype.bus=newVue）其实基于bus = new Vue）其实基于bus=newVue）其实基于on与$emit
vuex  状态管理实现通信
````

## 路由vue-router  

vue有两种路由模式，分别是hash和history,都是不刷新页面来更新页面，通过js实现动态网页内容
### hash模式
hash指的是域名地址#符号后面的值，作为锚点来跳转页面，通过监听window.location.hash变化，方法是onhashChange  
### history模式
