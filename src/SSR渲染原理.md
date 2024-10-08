
## CSR客户端渲染

页面渲染是JS负责进行的，浏览器发送请求–>服务器返回HTML–>浏览器发送bundle.js请求–>服务器返回bundle.js–>浏览器执行bundle.js中的react代码完成渲染；

弊端：
1. 由于页面显示过程要进行JS文件拉取和React代码执行，在这个渲染过程中至少涉及到两个 HTTP请求周期（html+js），所以会有一定的耗时，首屏加载时间会比较慢。
2. 对于SEO(Search Engine Optimazition,即搜索引擎优化)，完全无能为力，因为搜索引擎爬虫只认识html结构的内容，而不能识别JS代码内容。

## SSR服务端渲染

服务器端直接返回HTML让浏览器直接渲染；浏览器发送请求–>服务器运行React代码生成页面–>服务器返回页面。

弊端：


在 React 中使用 ssr 技术，我们让 React 代码在服务器端先执行一次，使得用户下载的 HTML 已经包含了所有的页面展示内容，这样，页面展示的过程只需要经历一个 HTTP 请求周期，TTFP（Time To First Page） 时间得到一倍以上的缩减

但是使用 ssr 这种技术，将使原本简单的 React 项目变得非常复杂
1. 相对于仅仅需要提供静态文件的服务器，ssr中使用的渲染程序自然会占用更多的CPU和内存资源
2. 在服务器生成的页面所以，一些常用的浏览器API可能无法正常使用，比如window、docment和alert等，如果使用的话需要对运行的环境加以判断
3. 开发调试会有一些麻烦，因为涉及了浏览器及服务器，对于SPA的一些组件的生命周期的管理会变得复杂
4. 可能会由于某些因素导致服务器端渲染的结果与浏览器端的结果不一致，项目的可维护性会降低，代码问题的追溯也会变得困难

所以，使用 ssr 在解决问题的同时，也会带来非常多的副作用，有的时候，这些副作用的伤害比起 ssr 技术带来的优势要大的多。一般建议ssr，除非你的项目特别依赖搜索引擎流量，或者对首屏时间有特殊的要求，否则不建议使用 ssr,如果只对seo有要求可使用[prerender预渲染](https://github.com/prerender/prerender)。


