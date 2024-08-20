
Virtual DOM不是真实的DOM但是却以对象的形式描述着DOM的特征。

```html
<!--> 真实DOM <-->
<div class="vnode" id="vnode">Hello VDOM</div>
```

```js
// 虚拟DOM
{
	tag:'div',
	props:{
		id: 'vnode',
		class: 'vnode,
	},
	children:['Hello VDOM']
}
```

> 为什么需要虚拟DOM？
> 浏览器向JS提供了各种各样的接口，去操作DOM。但是浏览器频繁调用这些API的同时，还会去做计算、布局、绘制、栅格化、合成等操作
