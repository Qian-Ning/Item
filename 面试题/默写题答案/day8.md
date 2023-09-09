vue

1. 计算属性如何传参: 计算属性 (computed properties) 在 Vue 中是一种基于其依赖项进行缓存的属性，只有当依赖项改变时，计算属性才会重新计算。你不能直接向计算属性传递参数，因为它们是基于其依赖项进行计算的。但是，你可以在计算属性内部使用函数的参数。例如：


```javascript
computed: {
  fullName: function() {
    return this.firstName + ' ' + this.lastName;
  }
}
```
在上面的例子中，`fullName` 是一个计算属性，它基于 `firstName` 和 `lastName` 这两个依赖项进行计算。
2. v-model的原理: `v-model` 是 Vue 中的一个指令，用于在表单控件元素上创建双向数据绑定。`v-model` 的原理是：它在内部使用了 `Object.defineProperty()` 方法来劫持数据的 setter 和 getter，并通过监听 input 事件来更新数据。当数据发生改变时，它会触发一个更新循环，从而更新视图。
3. style标签的scoped作用和原理是什么: 在 Vue 中，`<style>` 标签的 `scoped` 属性用于限制 CSS 样式只作用于当前组件。这是通过给当前组件的 HTML 元素添加一个唯一的属性（例如 `data-v-21e5b78`）来实现的。然后，在 CSS 中可以使用这个唯一的属性来限制样式只作用于当前组件。例如：


```css
<style scoped>
.example {
  color: red;
}
</style>
```
上面的代码会编译成：


```css
<style>
.example[data-v-21e5b78] {
  color: red;
}
</style>
```
4. 在scoped的条件下如何修改子组件内的样式 (如何修改element-ui(组件库)组件样式): 要修改子组件内的样式，可以使用 CSS 的样式作用域（例如使用 `<style scoped>` 或者在 CSS 中使用更具体的选择器）。如果要修改 Element UI 组件库的组件样式，可以通过覆盖组件的 CSS 类名来实现。例如：


```css
<style scoped>
/* 修改 Element UI 中的 Button 组件样式 */
.el-button {
  background-color: blue;
}
</style>
```
5. v-for与v-if的连用需要注意什么?: 在 Vue 中，`v-for` 和 `v-if` 可以一起使用，但是在性能上可能会产生一些问题。因为 `v-for` 比 `v-if` 的优先级更高，所以当它们一起使用时，`v-for` 会先执行。这可能会导致在每次迭代时都重新计算 `v-if` 条件，从而导致性能问题。因此，如果可能的话，最好将 `v-if` 移动到 `v-for` 循环的外面，以提高性能。

js

1. 深浅拷贝是编程中非常常见的概念，尤其是在处理对象和数组时。浅拷贝（Shallow Copy）只复制对象或数组的引用，而不是实际的内容。这就意味着，如果你改变原始对象或数组，那么拷贝出来的对象或数组也会改变。JavaScript 中的 Object.assign() 方法就是一个浅拷贝的例子。深拷贝（Deep Copy）则会复制对象或数组的实际内容，而不仅仅是引用。改变原始对象或数组不会影响到深拷贝出来的对象或数组。在 JavaScript 中，可以使用 JSON.parse(JSON.stringify(object)) 或者使用第三方库如 lodash 的 _.cloneDeep() 方法来实现深拷贝。
2. 闭包（Closure）是 JavaScript 中的一个重要概念，它是指一个函数可以访问并操作它创建时的词法环境，即使这个函数是在其词法环境之外执行的。闭包在很多地方都有用过，比如用于封装私有变量，创建工厂和模块等等。
3. 高阶函数（Higher-Order Function）是指可以接受其他函数作为参数，或者返回一个函数的函数。在 JavaScript 中，函数是一等公民，可以作为参数传递，也可以作为返回值。这种特性使得 JavaScript 非常适合于函数式编程风格，高阶函数就是其中的一种体现。例如，数组的 map()、filter()、reduce() 方法都是高阶函数的例子。

css

1. CSS动画有以下属性：


	* `animation-name`: 用于定义动画的名称。
	* `animation-duration`: 用于定义动画完成一个周期所需的时间。默认值是0，意味着没有动画。你可以指定具体的时间值，比如2s，300ms等。
	* `animation-timing-function`: 用于定义动画的速度曲线。常见的值有linear，ease，ease-in，ease-out，ease-in-out等。
	* `animation-delay`: 用于定义动画在开始前等待的时间。默认值是0，意味着动画立即开始。你可以指定具体的时间值，比如2s，300ms等。
	* `animation-iteration-count`: 用于定义动画播放的次数。你可以指定具体的数字，或者使用infinite来表示无限次播放。
	* `animation-direction`: 用于定义动画是否应该倒放。常见的值有normal，reverse，alternate和alternate-reverse。
	* `animation-fill-mode`: 用于控制动画在播放前后的状态。常见的值有none，forwards，backwards和both。
	* `animation-play-state`: 用于让动画播放（running）或者暂停（paused）。
2. CSS选择器有以下几种：


	* 元素选择器：通过HTML元素名称来选择元素。
	* 类选择器：通过类属性来选择元素。
	* ID选择器：通过ID属性来选择元素。
	* 属性选择器：通过元素属性来选择元素。
	* 伪类选择器：通过元素的特定状态来选择元素，例如:hover, :active, :visited等。
	* 伪元素选择器：通过元素的特定部分来选择元素，例如::before, ::after等。
	* 组合选择器：通过以上几种选择器进行组合使用，例如后代选择器（空格），子元素选择器（>），相邻兄弟选择器（+），通用兄弟选择器（~）等。
3. CSS的优先级计算规则如下：


	* 内联样式（在HTML元素内部）比任何其他样式都有更高的优先级。
	* ID选择器比属性选择器和类选择器优先级高。
	* 类选择器比标签选择器优先级高。
	* 在规则的权重相同的情况下，后出现的规则会覆盖先出现的规则。
	* 任何规则都不能覆盖内联样式，除非使用`!important`规则。
	* `!important`规则可以覆盖任何其他的CSS样式规则。
4. 浮动（float）是CSS的一种布局技术，可以让元素向左或向右移动，使文本或其他元素环绕它。浮动常用于创建多列布局。浮动元素会脱离文档流，导致其父元素高度塌陷，这就是为什么要清除浮动。清除浮动的方法有几种：


	* 使用clear属性：在浮动元素后面添加一个元素，并为其设置clear属性，值为left、right、both之一，以清除前面的浮动影响。
	* 使用BFC（块级格式上下文）：为父级元素创建一个BFC，可以清除其内部的浮动影响。可以通过将overflow设置为auto或hidden来创建BFC。
	* 使用clearfix类：在HTML中定义一个clearfix类，用于清除浮动影响。该方法结合了使用clear属性和使用BFC的方法。