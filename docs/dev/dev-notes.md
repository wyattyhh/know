---
layout: default
title: Dev Notes
parent: Dev
---

- css属性选择器 #css
	```javascript
	<div class="test" :someParams="true"><div/>
	
	.test {
		&[someParams="true"] {
			color: red
		}
	}
	```

- 直接在vue页面使用方法的话每次渲染都会执行一次方法,最好用computed替代. #vue 
	```html
	<div>{{getSum()}}</div>
	```

- Vue事件传参 #vue 
	 1. 不带圆括号时, event对象将被自动当作实惨传入. @click="onClick"  
	 2. 带圆括号时, 需要使用$event变量显式传入event对象. @click="onClick($event, val)"

- Enable `draggable` in parent node, but prevent drag on certain child node.
```jsx
	<div draggble="true" ref="dragWrap">
		<table 
			@mouseenter="setDraggable(false)"
			@mouseleave="setDraggable(true)"
		/>
	</div>

function setDraggble(boolean) {
	this.$refs.dragWrap.draggable = boolean
}
```