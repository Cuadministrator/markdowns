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

## CSS动画

- [CSS动画技巧和细节](https://github.com/chokcoco/iCSS/issues/27)
