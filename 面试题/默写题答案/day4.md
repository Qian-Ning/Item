#### vue

1. `$route`与`$router`的区别

`$route`是“路由信息对象”，包括当前激活的路由的状态信息，如匹配的路由记录、当前的路径、查询参数等。`$router`是VueRouter的实例，可以通过它访问路由的API。

2. 如何定义动态路由，如何获取传递过来的参数

在Vue Router中，使用冒号`:`来表示动态路由。例如：`/users/:id`，其中`:id`就是一个动态路由。获取传递过来的参数可以通过`this.$route.params.id`获取。

3. vue-router在组件中的钩子函数有哪些

在vue-router中，有以下的钩子函数：`beforeRouteEnter`、`beforeRouteUpdate`、`beforeRouteLeave`。

4. 路由传参的时候，params与query的区别

params是通过路径参数传递的，例如`/users/:id`，query是通过查询参数传递的，例如`/users?id=123`。params传递的参数会被包含在路径中，query传递的参数会被包含在查询字符串中。

5. vue-router的导航守卫有哪些

vue-router的导航守卫包括：全局的、单个路由独享的、组件内的。

6. vue-router的懒加载如何实现

使用动态import语法实现路由懒加载。在路由配置中，使用`component: () => import('@/views/Foo.vue')`实现。

7. 路由的hash和history模式的区别 (vue-router的原理)

hash模式是一种基于URL的锚点，#后面的内容在服务器会被自动忽略，因此后端如果没有正确的配置，访问时会返回404。history模式是HTML5新增的模式，通过HTML5 history API实现，后端需要配置支持。

#### js

1. for...in与for...of的区别

for...in用来遍历对象可枚举属性，返回的是属性名（字符串），可以遍历数组，但是并不推荐这样使用，因为它总是将数组视为对象。for...of用来遍历可迭代对象（包括Array，Map，Set，String，TypedArray，arguments对象等等），返回的是值。

2. 如何使用for...of遍历对象

使用for...of遍历对象的示例代码如下：

```js
let obj = {a: 1, b: 2, c: 3};
for (let value of Object.values(obj)) {
  console.log(value); // 1, 2, 3
}
```
3. 数组遍历方法有哪些

forEach、map、filter、reduce、every、some、find、findIndex等。

4. forEach与map方法的区别

forEach方法用于执行提供的函数对数组的每个元素，但不返回任何值。map方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。

5. ‘use strict’是什么意思，使用它区别是什么?

'use strict'是一种指令，在JS文件中使用它，表示该文件中的所有代码都按照严格模式进行解析和执行。区别包括：严格模式下，变量必须声明才能使用；函数中的this不再指向全局对象；严格模式下，eval和arguments的行为会有变化；严格模式下，一些可能会导致语法错误的情况会抛出错误等。