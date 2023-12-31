#### vue

1. mixin是一种复用技术，可以在多个组件中复用相同的js代码，可以将一些公共方法、计算属性、生命周期钩子函数等抽取到mixin中，实现代码复用。
2. watch属性包括：
* handler：函数，被监听的数据变化后执行的回调函数。
* deep：布尔值，决定是否监听对象内部值的变化。
* immediate：布尔值，决定是否在实例刚创建时就执行监听函数。
* lazy：布尔值，延迟执行监听函数，直到数据发生变化时才执行。
3. vue的生命周期包括：
* beforeCreate：实例刚创建时调用，此时还没有调用data选项中定义的数据和methods方法中定义的方法。
* created：实例创建完成后调用，此时已经完成了数据的观测，但是尚未挂载DOM，$el属性尚不可用。
* beforeMount：在挂载之前调用，相关的render函数首次被调用。可以在此时对实例进行渲染。
* mounted：实例已经挂载到DOM上后调用。在这个时候所有可以用到的模板都被渲染好，并通过$el属性进行访问。
* beforeUpdate：状态更新之前调用，此时已完成数据的发送变化。在这个生命周期中，可以对组件的DOM进行同步，或修改已有的DOM元素，或更新状态。
* updated：组件DOM已经更新，此时可以执行依赖于DOM的操作。在大多数情况下，应该避免在此期间更改状态，因为这可能会导致更新无限循环。
* beforeDestroy：实例销毁之前调用。在这个周期中，可以执行必要的清理工作，比如取消计时器、移除事件监听器等。
* destroyed：实例已经销毁之后调用。这个周期中，所有的事件监听器和子组件都被移除，所以，组件可以进行善后工作，比如清除计时器和清除DOM元素。
4. $nextTick是Vue中的一个方法，用于在下一个DOM更新循环结束后延迟执行一段代码。这个方法可以用于在数据变化后等待DOM更新完成后再进行操作，比如获取DOM元素的状态或者执行依赖于DOM的操作。
5. 虚拟DOM是一种技术，使用JS对象来模拟真实DOM的结构和属性，通过比较新旧虚拟DOM的差异来更新真实DOM，从而减少直接操作真实DOM的次数，提高性能。
6. key是Vue中用于优化列表渲染的一种机制。当Vue使用v-for指令渲染一个数组时，它默认使用“就地复用”策略，即如果数据项的顺序改变，Vue不会移动DOM元素来匹配数据项的顺序，而是简单复用已有的元素。这种策略在某些情况下会导致渲染错误。为了避免这种情况，可以使用key属性来为每个元素指定一个唯一的标识符，Vue会根据key属性的值来重新排列元素顺序。
7. 不建议使用index作为key值是因为如果数组的元素顺序改变，index值也会跟着改变，这样就会导致Vue无法正确地复用元素，从而导致渲染错误。

#### js

1. 数组尾部操作方法有push()和unshift()。push()方法用于在数组的末尾添加一个或多个元素，并返回新的长度；unshift()方法用于在数组的开头添加一个或多个元素，并返回新的长度。
2. 数组首部操作方法有shift()和unshift()。shift()方法用于删除并返回数组的第一个元素；unshift()方法用于在数组的开头添加一个或多个元素，并返回新的长度。
3. 数组连接方法有concat()和join()。concat()方法用于连接两个或更多的数组，并返回一个新的数组；join()方法用于把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。
4. 数组截取方法有slice()和splice()。slice()方法用于选取数组的的一部分，并返回一个新数组；splice()方法用于添加/删除数组的元素。
5. 数组插入方法有splice()。splice()方法可以在任意位置插入任意数量的元素。
6. 数组归并方法有reduce()和reduceRight()。reduce()方法对数组中的每个元素执行一个由您提供的reducer函数(升序执行)，将其结果汇总为单个返回值；reduceRight()方法对数组中的每个元素执行一个由您提供的reducer函数(降序执行)，将其结果汇总为单个返回值。
7. 查找数组特定元素的方法有indexOf()和find()。indexOf()方法返回在数组中可以找到给定元素的第一个索引，如果不存在，则返回-1；find()方法返回数组中满足提供的测试函数的第一个元素的值。否则返回undefined。