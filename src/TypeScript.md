> Ts语法知识在js的基础上增加了更多类型定义方面的内容，以此保证程序的类型安全。

# 核心内容

**类型定义**

```ts
const name:string = 'qianyu'
const age:number = 18
```

**类型联合与交叉**

```ts
// 类型联合
let myNumber: string | number;

// 类型交叉
type NameProtocal = {name: string}
type PersonLikeProtocal = {age: number; say: () => void}

type Student = NameProtocal & PersonLikeProtocal
```


类型推导(不建议依赖这个特性)
```ts
function sum(a:number,b:number) { // ts会自动推导返回值的类型
	return (a + b) .toString();
}

function sum(a:number,b:number) :string{
	return (a + b) .toString();
}
```


```ts
// interface 外联接口
interface Person {
	name: string;
	age?: number;
}
let person: Person;
person = {
	name: 'qianyu'
}

// 内联类型
let person2: {
	name:string;
	age:string;
}={
	name: 'qianyu',
	age: 22
}
```


