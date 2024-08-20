> SSR 服务端渲染：返回整个html骨架和内容，就可以提前渲染内容，提升首屏加载的速度。利于SEO，爬取页面内容。
> 
> CSR 客户端渲染：页面拿到的只有一个 空的根结点：root -> 执行js -> 虚拟DOM挂载到真实DOM -> 页面绘制 -> 看到实际内容。

目前常见的项目都是SPA工程(单页面应用程序)，保证了快速响应、开发效率、和交互体验。但是对SEO支持差，页面只有一个根结点，不利于爬虫爬取页面内容。

> 为什么要使用SSR？

更好的SEO、首屏渲染速度加快、端快照 =》 对用户体验更有好

> SSR渲染的基本过程

hydreate 会在渲染过程中，不再创建html标签，而是关联已有的内容，避免不必要的渲染
服务端渲染的组建时 string 拼接成 html返回，浏览器渲染出返回的html 执行hydreate

前端：React使用 ReactDom.hydrateRoot
后端：React ReactDOM.renderToString

## 原理

server (服务端)处理虚拟DOM -> 转成真实的DOM

