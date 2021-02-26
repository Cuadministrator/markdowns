# ES6

## 迭代器 for...of

- Array、Set、Map、argument 原型上有Symbol.iterator标识, 且有默认iterator实现

```javascript
const todo = {
  life: ['吃饭', '睡觉', '打豆豆'],
  learn: ['语文'， '数学', '英语'],
  work: ['摸鱼'],

  [symbol.iterator]: () => {
    const all = [...this.life, ...this.learn, ...this.work]
    let index = 0
    return {
      next: () => {
        return {
          value: all[index],
          done: index++ >= all.length,
        }
      }
    }
  }
}

for (todo of item) {
  console.warn(item)
}
```