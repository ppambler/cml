### ✍️ Tangxt ⏳ 2021-12-17 🏷️ uni-app

# uni-app

> [HBuilderX - 知乎](https://www.zhihu.com/topic/20746230/hot)

1）uni-app 中的生命周期？

- [uniapp 中的一些生命周期理解 - 简书](https://www.jianshu.com/p/0366b9bc9a15)
- [生命周期 - uni-app 官网](https://uniapp.dcloud.io/collocation/frame/lifecycle?id=%e7%bb%84%e4%bb%b6%e7%94%9f%e5%91%bd%e5%91%a8%e6%9c%9f)

2）事件处理？

- [uni-app 组件的封装——父子组件之间事件的传递_World_Mei 的博客-CSDN 博客_uniapp 子组件事件](https://blog.csdn.net/World_Mei/article/details/105847761)
- [自定义组件如何支持 uniapp 的事件处理器？ - DCloud 问答](https://ask.dcloud.net.cn/question/114803)
- [uni-app 封装组件中点击事件及父子组件传值_YL-CSDN 博客_uniapp 组件点击事件](https://blog.csdn.net/qq_32195805/article/details/112471259)

3）hbuilderx 每次点保存，下面控制台就弹出来了？

下方控制台的大小可以改变的，用鼠标把它拉到底隐藏就行了

➹：[hbuilderx 每次点保存，下面控制台就弹出来了，好烦人啊，艹，怎么把它关了？？ - 知乎](https://www.zhihu.com/question/460538757/answer/2075075456

4）nvue 是啥？

uni-app 是逻辑和渲染分离的。渲染层，在 app 端提供了两套排版引擎：小程序方式的 webview 渲染，和 weex 方式的原生渲染。

两种渲染引擎可以自己根据需要选。vue 文件走的 webview 渲染，nvue 走的原生渲染。

组件和 js 写法是一样的，css 不一样，原生排版的能用的 css 必须是 flex 布局，这是 web 的 css 的子集。当然什么界面都可以用 flex 布出来。不懂 flex 布局就自己学。

一般情况下用 vue 就可以了。如果是 app 且有部分场景 vue 页面的性能不满足你的需求时，这个页面可以改用 nvue 页面。如果 app 里同时存在同名的 vue 和 nvue 页面，在 app 端会优先执行 nvue 页面，而其他端仍然优先 vue 页面。

> 官方推荐在 APP 使用 nvue，小程序和 H5 端使用 vue

➹：[uniapp 里 nvue 和 vue 的关系是什么啊？为什么有 vue 文件了还要再重新为 app 单独写一份 nvue 呢 - DCloud 问答](https://ask.dcloud.net.cn/question/69854)

➹：<https://uniapp.dcloud.io/nvue-outline>