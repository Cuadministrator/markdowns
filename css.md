# CSS

## 限制高度图片的拉伸问题

1. object-fit 属性指定元素的内容应该如何去适应指定容器的高度与宽度。

- object-fit: cover 被替换的内容在保持其宽高比的同时填充元素的整个内容框。如果对象的宽高比与内容框不相匹配，该对象将被剪裁以适应内容框。

```css
img {
  width: 20px;
  height: 20px;
  object-fit: cover;
  object-position: 50% 50%;
}
```

## 响应式

- [前端基础知识概述 -- 移动端开发的屏幕、图像、字体与布局的兼容适配](https://github.com/chokcoco/cnblogsArticle/issues/25)

### 图片

1. srcset
2. sizes

```html
<img src='photo@1x.png' srcset='photo@1x.png 1x, photo@2x.png 2x, photo@3x.png 3x' sizes="(min-width: 600px) 600px, 300px">
```

## 滚动优化

- scroll-behavior: smooth; 滚动框通过一个用户代理预定义的时长、使用预定义的时间函数，来实现平稳的滚动

- scroll-snap-type CSS 属性定义在滚动容器中的一个临时点（snap point）如何被严格的执行.(* 浏览器不完全支持)

## 动画

- [CSS动画技巧和细节](https://github.com/chokcoco/iCSS/issues/27)

## font-size: 0

### 涉及到的css属性

- font-size

- vertical-align

- line-height

### 原理

- 以下的所有都在 display: inline-block; 的布局情况下。

- 提出一个概念，在inline-block的布局情况下，图片前后(?)有所谓的【空白幽灵节点】

- vertical-align 的默认值为 base-line, base-line 的布局样式呈现，图片的下边，紧贴文字 (字符默认是行内元素) 的下边，文字在设置默认 font-size 的情况下会有line-height, 行高会导致文字产生额外的上下高度, 同理可得，图片后的幽灵节点也会出现了额外的上下高度，继而影响了图片下的额外高度。

### 解决方案

- 由原理可以想到的得到解决方法

1. 最简单能想到的方法是，将图片前后的【空白幽灵节点】设置的 line-height, 可以控制图片下的额外高度

2. 设置 font-size: 0 也是通过设置 line-height 来解决问题。

3. 当 vertical-align 不为 base-line 时可以解决这个问题，bottom / top / middle

4. 其次，当 元素不为行内元素 的时候就不存在前后的【空白幽灵节点】, 进而就没有这个问题了