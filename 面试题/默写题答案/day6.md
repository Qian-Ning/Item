#### vue

1. uniapp的条件编译是什么

条件编译是一种编程技术，它允许在编译时根据特定的条件选择性地编译代码。在uni-app中，条件编译用于在不同的平台（如微信小程序、H5、App等）上编写特定的代码，从而实现在不同平台上的适配。

2. rpx、px、em、rem、%、vh、vw的区别是什么？

* `rpx`：微信小程序中的尺寸单位，类似于px，但会根据设备的像素密度进行自适应调整。
* `px`：像素单位，绝对长度，不随屏幕大小变化。
* `em`：相对长度单位，相对于当前元素的字体大小。
* `rem`：相对长度单位，相对于根元素的字体大小。
* `%`：百分比单位，相对于父元素的尺寸。
* `vh`：视口高度单位，1vh等于视口高度的1%。
* `vw`：视口宽度单位，1vw等于视口宽度的1%。
3. uniapp中封装接口请求相较于微信小程序有什么要注意的 (和跨域相关)

在uni-app中封装接口请求时，相较于微信小程序，主要需要注意跨域问题。由于uni-app是基于Vue.js开发的，因此可以使用axios等HTTP库来进行接口请求。为了避免跨域问题，可以在后端服务器设置CORS（跨域资源共享）头信息，或者在uni-app中使用代理服务器来转发接口请求。

4. uniapp如何获取节点信息

在uni-app中，可以使用`uni.createSelectorQuery()`方法来获取节点信息。该方法返回一个`SelectorQuery`对象，可以使用该对象的`select()`方法选择节点，然后使用`boundingClientRect()`方法获取节点的位置和大小信息。最后，使用`exec()`方法来执行查询并获取结果。

5. uniapp上传文件的api是什么

在uni-app中，可以使用`uni.uploadFile()`API来上传文件。该API接受一个对象作为参数，其中包含要上传的文件的路径、文件名、文件类型等信息，以及要上传到的服务器的URL。可以使用该API的返回值来获取上传进度和上传结果。

6. uniapp中如何路由传参

在uni-app中，可以使用`uni.navigateTo()`和`uni.redirectTo()`方法来进行页面跳转，并通过这些方法的参数来传递数据。例如，可以使用`uni.navigateTo({ url: 'pages/detail/detail?id=123&name=test' })`方法跳转到详情页面，并在URL中传递`id`和`name`参数。在详情页面中，可以使用`this.$route.query.id`和`this.$route.query.name`来获取传递的参数。

7. uniapp如何上拉加载

在uni-app中，可以使用`uni.startPullDownRefresh()`方法来触发上拉加载。该方法可以在页面加载完成后调用，以启动上拉加载动画。在上拉加载完成后，可以使用`uni.stopPullDownRefresh()`方法来停止上拉加载动画。

8. uniapp如何下拉刷新

在uni-app中，可以使用`uni.startReachBottomRefresh()`方法来触发下拉刷新。该方法可以在页面加载完成后调用，以启动下拉刷新动画。在下拉刷新完成后，可以使用`uni.stopReachBottomRefresh()`方法来停止下拉刷新动画。

#### js

1. js的基本数据类型

JavaScript的基本数据类型包括：

* Number：数值类型，包括整数和浮点数。
* String：字符串类型，用于表示文本数据。
* Boolean：布尔类型，用于表示真或假两种状态。
* Null：空类型，表示空值。
* Undefined：未定义类型，表示未定义的值。
* Symbol：符号类型，用于表示唯一的标识符。
* BigInt：大整数类型，用于表示超过Number类型能表示的整数范围的数值。
2. 什么是隐式转换

隐式转换是指在表达式中自动将一种数据类型转换为另一种数据类型的过程，而不需要显式指定转换方式。例如，在JavaScript中，当一个字符串和一个数字相加时，会自动将字符串转换为数字，然后进行加法运算。这种自动转换就是隐式转换。

3. Typeof 的检测结果是什么? 

`typeof`是JavaScript中的一个运算符，用于检测一个变量的类型。`typeof`的检测结果是一个字符串，表示变量的类型。例如，对于数值类型的变量，`typeof`的检测结果是`"number"`；对于字符串类型的变量，`typeof`的检测结果是`"string"`；对于布尔类型的变量，`typeof`的检测结果是`"boolean"`；对于对象类型的变量，`typeof`的检测结果是`"object"`；对于函数类型的变量，`typeof`的检测结果是`"function"`；对于未定义类型的变量，`typeof`的检测结果是`"undefined"`；对于空类型的变量，`typeof`的检测结果也是