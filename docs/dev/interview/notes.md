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
