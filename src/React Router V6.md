https://reactrouter.com/en/6.26.1

不同的react-router包：
1. `react-router-dom`：针对浏览器的包
2. `react-router-native`：针对 `RN`跨端方案的包 ios、android

创建路由的方式：
1. *函数式*：更方便`权限管理`、`ts类型推倒`更加健全
2. 组件式：像HTML标签一样 一个套一个

## 常见的路由

`createBrowserRouter`: 底层基于 dom 的 history api 更新url，并且管理历史堆栈

`createHashRouter`: 基于hash路由状态管理

`createMemoryRouter`: 内存型路由，不使用浏览器历史记录。在内存中管理历史堆栈，(测试和组件开发中可能会用)

`createStaticRouter`:  服务端路由，主要用于[[SSR渲染原理]]

## Router包架构设计

![[Router架构设计.excalidraw | 1000]]

## `BrowserRouter`原理

![[BrowserRouter.excalidraw | 1000]]


---
> 单页面和多页面的区别：

单页面：只有一个HTML文件，通过js去控制。==（SPA工程项目）==
- 好处：页面跳转不用刷新，性能会好一些，用户体验也相对较好。可以实现代码复用
- 缺点：对SEO不友好

多页面：多页面就是多个HTML文件，通过window.location互相跳转。
- 好处：对SEO更友好，隔离性好，每一个页面都是一个独立的项目。
- 缺点：每个页面跳转都要刷新，重新加载资源，性能会比较慢

> 打包出来的文件，路由不能跳转？

如果是`createBrowserRouter`需要在`nginx`上添加
```
// 让所有的请求都指向index.html, index.html对访问的路径进行匹配 渲染出对应的组件
location / {
	try_files $uri /index.html;
}
```


---
## 补充资料
[React Router官网](https://reactrouter.com/en/6.26.1)
[[SSR渲染原理]]