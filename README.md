# akicons

iconfont for Arknights. Made by [iconfont](https://www.iconfont.cn/)

[Demo|示例页面](https://nemo1166.github.io/akicons/)

## 版权声明

明日方舟、Arknights及其相关素材所有权归属于上海鹰角网络科技有限公司，本项目旨在辅助基于《明日方舟》的二次创作，请在合理范围内使用本项目素材。[参考](https://www.hypergryph.com/service)

## 用法

### Unicode 引用

Unicode 是字体在网页端最原始的应用方式，特点是：

- 支持按字体的方式去动态调整图标大小，颜色等等。
- 默认情况下不支持多色，直接添加多色图标会自动去色。
- 注意：新版 iconfont 支持两种方式引用多色图标：SVG symbol 引用方式和彩色字体图标模式。（使用彩色字体图标需要在「编辑项目」中开启「彩色」选项后并重新生成。）

定义使用 iconfont 的样式

```css
@font-face {
  font-family: 'iconfont';
  src: url('https://unpkg.com/akicons@1.0.0/iconfont.woff2') format('woff2'),
       url('https://unpkg.com/akicons@1.0.0/iconfont.woff') format('woff'),
       url('https://unpkg.com/akicons@1.0.0/iconfont.ttf') format('truetype'),
       url('https://unpkg.com/akicons@1.0.0/iconfont.svg#iconfont') format('svg');
}

.iconfont {
  font-family: "iconfont" !important;
  font-size: 16px;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

挑选相应图标并获取字体编码，应用于页面

```html
<span class="iconfont">&#x33;</span>
```

### font-class 引用

font-class 是 Unicode 使用方式的一种变种，主要是解决 Unicode 书写不直观，语意不明确的问题。

与 Unicode 使用方式相比，具有如下特点：

- 相比于 Unicode 语意明确，书写更直观。可以很容易分辨这个 icon 是什么。
- 因为使用 class 来定义图标，所以当要替换图标时，只需要修改 class 里面的 Unicode 引用。

第一步：引入项目下面生成的 fontclass 代码：

```html
<link rel="stylesheet" href="https://unpkg.com/akicons@1.0.0/iconfont.css">
```

第二步：挑选相应图标并获取类名，应用于页面：

```html
<span class="iconfont icon-ak-xxx"></span>
```

### Symbol 引用

这是一种全新的使用方式，应该说这才是未来的主流，也是平台目前推荐的用法。相关介绍可以参考这篇文章 这种用法其实是做了一个 SVG 的集合，与另外两种相比具有如下特点：

- 支持多色图标了，不再受单色限制。
- 通过一些技巧，支持像字体那样，通过 font-size, color 来调整样式。
- 兼容性较差，支持 IE9+，及现代浏览器。
- 浏览器渲染 SVG 的性能一般，还不如 png。

使用步骤如下：

第一步：在`<head>`中引入项目下面生成的 symbol 代码：
```html
<script src="./iconfont.js"></script>
```
第二步：加入通用 CSS 代码

```css
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
```

第三步：挑选相应图标并获取类名，应用于页面：

```html
<svg class="icon" aria-hidden="true">
  <use xlink:href="#icon-xxx"></use>
</svg>
```
