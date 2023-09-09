#### vue

1. Vue如何给data中的对象添加一个新属性，并保证响应式

在Vue中，可以通过`Vue.set`或`this.$set`方法来给data中的对象添加一个新属性，这样可以确保新属性同样是响应式的。例如：


```javascript
Vue.set(this.someObject, 'newProp', 'new value')
// 或者
this.$set(this.someObject, 'newProp', 'new value')
```
2. Vue重写的数组方法有哪些

Vue重写了JavaScript的数组方法，包括：`push`、`pop`、`shift`、`unshift`、`splice`、`sort`、`reverse`。这些方法在Vue中都是响应式的，意味着当这些方法改变数组时，视图也会自动更新。

3. Vue中data发生改变的时候，视图会立刻执行重新渲染么?

是的，Vue使用数据劫持和发布订阅模式，当data发生改变时，会自动触发视图的重新渲染。

4. Vuex有哪些属性

Vuex是一个为Vue.js应用程序开发的状态管理模式。它包含以下属性：

* state：一个纯对象，用于存储应用程序的状态。
* getters：基于state的计算属性，用以执行更复杂的数据操作。
* mutations：修改state的唯一途径，必须是同步函数。
* actions：类似于mutations，可以包含任意异步操作。
* modules：将单一状态树分割成多个模块，每个模块拥有自己的state、mutation、action、getters。

5. Vuex中action与mutation的区别

Mutation和Action都是Vuex中改变state的方法。Mutation是同步函数，用于直接改变state。而Action可以包含任意异步操作，它通常通过调用Mutation来间接改变state。另外，Action可以包含任意异步操作，例如API请求等。

6. Vuex与localstorage的区别

Vuex是一个为Vue.js应用程序开发的状态管理模式，它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。而localStorage是浏览器提供的本地存储机制，它通常用于持久化存储数据，例如用户信息、应用配置等。Vuex和localStorage在数据存储的位置、存储方式、存储规则等方面都有所不同。

7. Vuex提供了几个mapxxx的方法，分别是做什么用的?

Vuex提供了几个mapxxx的方法，用于帮助我们生成计算属性和方法。包括：

* mapState：生成计算属性返回我们需要的状态值。
* mapGetters：生成计算属性返回我们需要的getter值。
* mapActions：生成组件的方法，调用我们需要的action。
* mapMutations：生成组件的方法，调用我们需要的mutation。

#### js

1. Promise的三种状态 (es6)

Promise有三种状态：pending（等待态）、fulfilled（完成态）、rejected（拒绝态）。一旦Promise的状态从pending变为fulfilled或rejected，就不会再次改变。

2. Promise实例的两种过程

Promise实例的两种过程是：从pending变为fulfilled的过程，和从pending变为rejected的过程。这两种过程都是不可逆的。一旦Promise的状态从pending变为fulfilled或rejected，就不会再次改变。

3. 如何创建Promise对象

可以通过new Promise()构造函数来创建Promise对象。例如：


```javascript
let promise = new Promise((resolve, reject) => {
  // 异步操作成功，调用resolve()方法改变Promise状态为fulfilled
  // 异步操作失败，调用reject()方法改变Promise状态为rejected
});
```
4. Promise实例有哪些方法

Promise实例有两个方法：then()和catch()。then()方法用于处理Promise对象成功的情况，catch()方法用于处理Promise对象失败的情况。这两个方法都返回一个新的Promise实例，因此可以链式调用。例如：


```javascript
promise.then((value) => {
  // 处理成功的情况
}).catch((error) => {
  // 处理失败的情况
});
```
5. 什么是Promise.all

Promise.all()方法是一个静态方法，用于将多个Promise实例包装成一个新的Promise实例。这个新的Promise实例的状态由多个Promise实例的状态决定。当所有的Promise实例都变成fulfilled或rejected状态时，新的Promise实例才会变成fulfilled或rejected状态。例如：


```javascript
let promise1 = new Promise((resolve, reject) => { /*...*/ });
let promise2 = new Promise((resolve, reject) => { /*...*/ });
Promise.all([promise1, promise2]).then((values) => {
  // 处理所有Promise实例都成功的情况
}).catch((error) => {
  // 处理任意一个Promise实例失败的情况
});
```
6. 什么是Promise.race

Promise.race()方法是一个静态方法，用于将多个Promise实例包装成一个新的Promise实例。