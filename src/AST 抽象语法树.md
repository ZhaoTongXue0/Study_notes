AST（Abstract Syntax Tree，抽象语法树）是一种用于表示代码结构的树状数据结构。它是编译器或解释器在代码分析和转换过程中生成的中间表示形式，能够捕捉源代码的语法结构，而不依赖于具体的语法细节。

> Babel is a JavaScript compiler

## compiler 编译器

作用：将用某种编程语言写成的源代码，转换成另一种编程语言。

## 编译器的基本思路

前端可以使用[[babel]]实现一下流程

1. 词法分析
2. 语法分析
3. 代码转换
4. 代码生成
5. 完整链路


```javascript
input => tokenizer => tokens; // 词法分析
tokens => parser => ast; // 语法分析，生成AST
ast => transformer => newAst; // 中间层代码转换
newAst => generator => output; // 生成目标代码
```

![[编译器的基本思路.excalidraw | 1000]]
