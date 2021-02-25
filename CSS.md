# CSS

## 限制高度图片的拉伸问题

1. object-fit 属性指定元素的内容应该如何去适应指定容器的高度与宽度。

```css
img {
  width: 20px;
  height: 20px;
  object-fit: cover;
  object-position: 50% 50%;
}
```

