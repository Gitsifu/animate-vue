# Vue集成animate.css、wow.js和move.js

参考资料（GitHub链接）

- [animate.css](https://github.com/animate-css/animate.css)
- [wow.js](https://github.com/matthieua/WOW)
- [move.js](https://github.com/visionmedia/move.js)

---

- [Animate中文网](http://www.animate.net.cn/)

# 概述
> animate.css 是一个来自国外的 CSS3 动画库，它预设了抖动（shake）、闪烁（flash）、弹跳（bounce）、翻转（flip）、旋转（rotateIn/rotateOut）、淡入淡出（fadeIn/fadeOut）等多达 60 多种动画效果，几乎包含了所有常见的动画效果。
>
>虽然借助 animate.css 能够很方便、快速的制作 CSS3 动画效果，但还是建议看看 animate.css 的代码，也许你能从中学到一些东西。
>
>在使用animate.css的时候通常都会搭配wow.js

同时wow.js在某些情况下可以配合move.js做更多的效果。

**注意**：animate.css版本3.x和4.x有区别，4.x的所有类名需要加上`animate__`的前缀，而3.x不需要。具体详见[animate.css官网](https://animate.style/)

## 下载依赖
```
npm install animate.css wow-js move-js --save
```

## 引入animate.css
在 main.js 中写入以下内容：
```
import 'animate.css'
```

## 引入wow.js
在 main.js 中写入以下内容：
```
import { WOW } from "wowjs";

new Vue({
  router,
  store,
  render: h => h(App),
  mounted() {
    new WOW({
      boxClass:     'wow',      // default
      animateClass: 'animate__animated', // default
      offset:       0,          // default
      mobile:       true,       // default
      live:         true        // default
    }).init()
  }
}).$mount('#app')
```

## 引入move.js
在组件中写入以下内容：
```
import move from 'move-js'

move('.square')
    .set('background-color', 'blue')
    .duration('4s')
    .end(function(){
        move('.square')
            .set('background-color', 'red')
            .end()
    });
```

## 运行
```
npm install

npm run serve
```
