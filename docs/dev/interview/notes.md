## HTML&CSS
### 盒模型
- 内容 Content, 内边距 Padding, 边框 Border, 外边距 Margin.
- 标准盒模型 content-box VS IE盒模型 border-box (content + padding + border)
### BFC 块级格式化上下文
独立的渲染区域, 内部元素不会影响外部. 
#### 如何触发BFC？

- `overflow: hidden`（最常用）
    
- `float: left/right`
    
- `display: flex/grid/inline-block`
    
- `position: absolute/fixed`

```html
**外边距折叠（Margin Collapse）**
<div class="a"></div> <!-- margin-bottom: 20px -->
<div class="b"></div> <!-- margin-top: 30px → 实际间距30px（非50px）-->
将其中一个元素包裹在BFC容器中可避免折叠
```

| 概念   | 核心作用      | 典型场景         |
| ---- | --------- | ------------ |
| 盒模型  | 控制元素尺寸与间距 | 所有布局基础       |
| Flex | 一维弹性布局    | 导航栏、等分卡片     |
| Grid | 二维网格布局    | 复杂仪表盘、响应式设计  |
| BFC  | 隔离布局，避免干扰 | 清除浮动、防止外边距折叠 |
| 居中对齐 | 元素在容器中居中  | 弹窗、登录框       |

### 响应式设计
#### 媒体查询(Media Queries)
根据设备特性(屏幕宽度) 应用不同的样式
```css
@media (max-width: 768px) {
	.contianer {
		width: 100%;
	}
}
```
#### REM vs EM
相对单位, em是相对父元素的字体大小, rem是相对根元素(html)的字体大小. 
项目中的应用一般是在移动端项目中, 动态设置根元素的字体大小, 同时使用rem实现自适应样式.
### CSS选择器优先级
1. `!important` 强制生效 (慎用).
2. 内联样式: 直接写在html标签的style属性中.
3. ID选择器(如`#header`): 权重100.
4. 类/伪类/属性选择器(如 `.class`、`:hover`、`[type="text"]`): 权重10.
5. 元素/伪元素选择器(如 `div`、`::before`): 权重1.
规则: 权重叠加比较, 权重高的生效; 权重相同时, 后定义的生效.
### 伪类 vs 伪元素
伪类(Pseudo-classes): 单冒号: , 选择元素的特定状态, 比如:hover, :focus, :first-child...
伪元素(Pseudo-elements): 双冒号:: , 创建虚拟元素, 比如::before, ::after, ::first-line.
### CSS动画
通过@keyframes定义动画, 用animation属性应用动画.

## Javascript
### 闭包 Closure
闭包就是函数定义时, 可访问外部的作用域. 实际应用有: 封装私有变量, 延长变量生命周期.
```js
function outer() { 
	let count = 0; 
	return function inner() { 
		count++; 
		console.log(count); 
		}; 
	} 
const fn = outer(); 
fn(); // 输出 1 
fn(); // 输出 2（count 未被销毁）
```
### 作用域链 Scope Chain
函数在查找变量时, 从自身作用域逐级向外查找.
### 原型链 Prototype Chain
访问属性时，若对象自身不存在，则沿原型链向上查找，直到 `null`
### this指向
- **普通函数**：默认指向调用者（如 `obj.method()` 的 `this` 是 `obj`），无调用者时非严格模式指向 `window`，严格模式为 `undefined`。
- **箭头函数**：继承定义时的外层 `this`，不可更改。
- **显式绑定**：`call`/`apply`/`bind` 可修改 `this`。
#### 显式绑定的应用
1. **改变回调函数的 `this` 指向**
```js
// 示例：React 类组件中绑定事件处理函数
class Button extends React.Component {
  constructor() {
    super();
    this.handleClick = this.handleClick.bind(this); // 绑定 this 为组件实例
  }
  handleClick() {
    console.log(this); // 指向组件实例
  }
  render() {
    return <button onClick={this.handleClick}>Click</button>;
  }
}

// 替代方案：使用箭头函数自动绑定 this（现代开发更常用）
handleClick = () => {
  console.log(this); // 自动绑定 this
};
```
2. 函数柯里化 (提前绑定部分函数)
```js
// 示例：预置第一个参数
function multiply(a, b) {
  return a * b;
}
const double = multiply.bind(null, 2); // 预置 a=2
console.log(double(3)); // 6（等价于 multiply(2, 3)）
```
3. 现代开发中，优先用箭头函数或 Class 属性语法（如 React）替代 `bind`。
### Event Loop 时间循环
JavaScript 单线程处理异步任务的方式。
- **同步任务**：在主线程立即执行。
- **异步任务**：分为宏任务（`setTimeout`、`DOM事件`）和微任务（`Promise.then`、`queueMicrotask`）。
- **执行顺序**：同步任务 → 所有微任务 → 一个宏任务 → 重复。
### Promise与Async/Await
#### 1. Promise
解决回调地狱, 用链式调用管理异步操作.
```js
// before
setTimeout(()=>{
	console.log('do something')
}, 1000)

// after
let p = new Promose
```

3. Async/Await

