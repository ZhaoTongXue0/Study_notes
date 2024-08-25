babel的原理[[AST 抽象语法树#编译器的基本思路]]

babel 7 之后，所以的babel包都在 `@babel`空间命名下

- `@babel/core`： babel的编译器 核心API
- `@babel/parser`： 接受源码 进行词法分析、语法分析、生成AST
- `@babel/traverse`：接受一个 AST 进行遍历，可以对节点进行修改、替换、添加
- `@babel/generator`：接受新的 AST 转换为代码字符串
- `@babel/types`：用于检验、构建和改变 AST树 的节点

## babel 插件

babel插件是一个简单的函数，返回一个对象
```js
/*
 * 接收的参数
 * api：一个对象，包含了 types (@babel/types)、traverse (@babel/traverse)、template(@babel/template) 等实用方法，我们能从这个对象中访问到 @babel/core dependecies 中包含的方法。
 * options：插件参数
 * dirname：目录名
 * 
 * 返回的对象
 * name：插件名字。
 * inherits：指定继承某个插件，通过 Object.assign 的方式，和当前插件的 options 合并。
 * visitor：指定 traverse 时调用的函数。
 * pre 和 post 分别在遍历前后调用，可以做一些插件调用前后的逻辑，比如可以往 file（表示文件的对象，在插件里面通过 state.file 拿到）中放一些东西，在遍历的过程中取出来。
 * manipulateOptions：用于修改 options，是在插件里面修改配置的方式。
 **/
export default function(api, options, dirname){
	return(
		name: '插件名字',
		pre(){},
		visitor:{
			// 访问者模式，访问的节点，对节点进行处理
		},
		post(){}, //遍历后调用
	)
}
```