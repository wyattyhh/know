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
