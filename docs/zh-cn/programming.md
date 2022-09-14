# 编程规范

# HTML 规范

参考 W3Cschool,具体请访问 [W3Cschool](https://www.w3cschool.cn/wematy/wematy-x9ne3bt0.html)

## 基本结构

### HTML5 标准模版

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>HTML5标准模版</title>
</head>
<body>

</body>
</html>
```

### HTML5 移动端 标准模版

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, shrink-to-fit=no" >
<meta name="format-detection" content="telephone=no" >
<title>移动端HTML模版</title>

<!-- S DNS预解析 -->
<link rel="dns-prefetch" href="">
<!-- E DNS预解析 -->
​
<!-- S 线上样式页面片，开发请直接取消注释引用 -->
<!-- #include virtual="" -->
<!-- E 线上样式页面片 -->
​
<!-- S 本地调试，根据开发模式选择调试方式，请开发删除 -->
<link rel="stylesheet" href="css/index.css" >
<!-- /本地调试方式 -->
​
<link rel="stylesheet" href="http://srcPath/index.css" rel="external nofollow" target="_blank"  rel="external nofollow" target="_blank"  >
<!-- /开发机调试方式 -->
<!-- E 本地调试 -->
​
</head>
<body>
​
</body>
</html>
```

### HTML5 PC 端 标准模版

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="keywords" content="your keywords">
<meta name="description" content="your description">
<meta name="author" content="author,email address">
<meta name="robots" content="index,follow">
<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
<meta name="renderer" content="ie-stand">
<title>PC端HTML模版</title>
​
<!-- S DNS预解析 -->
<link rel="dns-prefetch" href="">
<!-- E DNS预解析 -->
​
<!-- S 线上样式页面片，开发请直接取消注释引用 -->
<!-- #include virtual="" -->
<!-- E 线上样式页面片 -->
​
<!-- S 本地调试，根据开发模式选择调试方式，请开发删除 -->
<link rel="stylesheet" href="css/index.css" >
<!-- /本地调试方式 -->
​
<link rel="stylesheet" href="http://srcPath/index.css" rel="external nofollow" target="_blank"  rel="external nofollow" target="_blank"  >
<!-- /开发机调试方式 -->
<!-- E 本地调试 -->
​
</head>
<body>
​
</body>
</html>
```

# CSS 规范

参考 W3Cschool,具体请访问 [W3Cschool](https://www.w3cschool.cn/wematy/wematy-x9ne3bt0.html)

## 代码规范

- 样式文件必须写上 @charset 规则，并且一定要在样式文件的第一行首个字符位置开始写，编码名用 “UTF-8”
- 字符 @charset “”; 都用小写字母，不能出现转义符，编码名允许大小混写
- 考虑到在使用“UTF-8”编码情况下 BOM 对代码的污染和编码显示的问题，在可控范围下，坚决不使用 BOM。

```css
@charset "UTF-8";
​ .jdc {
}
```

## 代码风格

### 代码格式化

为单个 css 选择器或新申明开启新行

```css
#good .jdc,
.jdc_logo,
.jdc_hd {
  color: #ff0;
}
#bad .jdc,
jdc_logo,
.jdc_hd {
  color: #ff0;
}
.nav {
  color: #fff;
}
```

属性书写顺序
建议遵循以下顺序

```
布局定位属性：display / position / float / clear / visibility / overflow
自身属性：width / height / margin / padding / border / background
文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …
```

CSS3 浏览器私有前缀在前，标准前缀在后

```css
.jdc {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -o-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## CSS 重置样式

移动端

```
* { -webkit-tap-highlight-color: transparent; outline: 0; margin: 0; padding: 0; vertical-align: baseline; }
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin: 0; padding: 0; vertical-align: baseline; }
img { border: 0 none; vertical-align: top; }
i, em { font-style: normal; }
ol, ul { list-style: none; }
input, select, button, h1, h2, h3, h4, h5, h6 { font-size: 100%; font-family: inherit; }
table { border-collapse: collapse; border-spacing: 0; }
a { text-decoration: none; color: #666; }
body { margin: 0 auto; min-width: 320px; max-width: 640px; height: 100%; font-size: 14px; font-family: -apple-system,Helvetica,sans-serif; line-height: 1.5; color: #666; -webkit-text-size-adjust: 100% !important; text-size-adjust: 100% !important; }
input[type="text"], textarea { -webkit-appearance: none; -moz-appearance: none; appearance: none; }
```

PC 端

```
html, body, div, h1, h2, h3, h4, h5, h6, p, dl, dt, dd, ol, ul, li, fieldset, form, label, input, legend, table, caption, tbody, tfoot, thead, tr, th, td, textarea, article, aside, audio, canvas, figure, footer, header, mark, menu, nav, section, time, video { margin: 0; padding: 0; }
h1, h2, h3, h4, h5, h6 { font-size: 100%; font-weight: normal }
article, aside, dialog, figure, footer, header, hgroup, nav, section, blockquote { display: block; }
ul, ol { list-style: none; }
img { border: 0 none; vertical-align: top; }
blockquote, q { quotes: none; }
blockquote:before, blockquote:after, q:before, q:after { content: none; }
table { border-collapse: collapse; border-spacing: 0; }
strong, em, i { font-style: normal; font-weight: normal; }
ins { text-decoration: underline; }
del { text-decoration: line-through; }
mark { background: none; }
input::-ms-clear { display: none !important; }
body { font: 12px/1.5 \5FAE\8F6F\96C5\9ED1, \5B8B\4F53, "Hiragino Sans GB", STHeiti, "WenQuanYi Micro Hei", "Droid Sans Fallback", SimSun, sans-serif; background: #fff; }
a { text-decoration: none; color: #333; }
a:hover { text-decoration: underline; }
```

# js 规范

参考 W3Cschool,具体请访问 [W3Cschool](https://www.w3cschool.cn/wematy/wematy-x9ne3bt0.html)

## 引用

<font color="#e96900">const</font> 和 <font color="#e96900">let</font> 都是块级作用域，<font color="#e96900">var</font> 是函数级作用域

- 对所有引用都使用 <font color="#e96900">const</font>，不要使用 <font color="#e96900">var</font>

```js
// bad
var a = 1;
var b = 2;

// good
const a = 1;
const b = 2;
```

- 如果引用是可变动的，则使用 <font color="#e96900">let</font>

```js
// bad
var count = 1;
if (count < 10) {
  count += 1;
}

// good
let count = 1;
if (count < 10) {
  count += 1;
}
```

- 将所有的 const 和 let 分组

```js
// bad
let a
const b
let c
const d
let e

// good
const b
const d
let a
let c
let e
```

## 对象

- 请使用字面量值创建对象

```js
// bad
const a = new Object{}

// good
const a = {}
```

- 请使用对象方法的简写方式

```js
// bad
const item = {
  value: 1,

  addValue: function (val) {
    return item.value + val;
  }
};

// good
const item = {
  value: 1,

  addValue(val) {
    return item.value + val;
  }
};
```

- 请使用对象属性值的简写方式

```js
const job = 'FrontEnd';

// bad
const item = {
  job: job
};

// good
const item = {
  job
};
```

## 数组

- 请使用字面量值创建数组

```js
// bad
const items = new Array();

// good
const items = [];
```

- 向数组中添加元素时，请使用<font color="#e96900">push</font> 方法

```js
const items = [];

// bad
items[items.length] = 'test';

// good
items.push('test');
```

- 使用拓展运算符 <font color="#e96900">...</font> 复制数组

```js
// bad
const items = [];
const itemsCopy = [];
const len = items.length;
let i;

// bad
for (i = 0; i < len; i++) {
  itemsCopy[i] = items[i];
}

// good
itemsCopy = [...items];
```

## 结构赋值

- 当需要使用对象的多个属性时，请使用解构赋值

```js
// bad
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}

// good
function getFullName(user) {
  const { firstName, lastName } = user;

  return `${firstName} ${lastName}`;
}

// better
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
```

## 字符串

- 字符串太长的时候，请不要使用字符串连接符换行 <font color="#e96900">\\</font>，而是使用 <font color="#e96900">\+</font>

```js
const str =
  '凹凸实验室 凹凸实验室 凹凸实验室' +
  '凹凸实验室 凹凸实验室 凹凸实验室' +
  '凹凸实验室 凹凸实验室';
```

- 程序化生成字符串时，请使用模板字符串

```js
const test = 'test';

// bad
const str = ['a', 'b', test].join();

// bad
const str = 'a' + 'b' + test;

// good
const str = `ab${test}`;
```

## 函数

- 请使用函数声明，而不是函数表达式

```js
// bad
const foo = function () {
  // do something
};

// good
function foo() {
  // do something
}
```

- 不要更改函数参数的值

```js
// bad
function test(opts) {
  opts = opts || {};
}

// good
function test(opts = {}) {
  // ...
}
```

## 原型

- 使用 <font color="#e96900">class</font> ，避免直接操作 <font color="#e96900">prototype</font>

```js
// bad
function Queue (contents = []) {
  this._queue = [..contents]
}
Queue.prototype.pop = function () {
  const value = this._queue[0]
  this._queue.splice(0, 1)
  return value
}

// good
class Queue {
  constructor (contents = []) {
    this._queue = [...contents]
  }

  pop () {
    const value = this._queue[0]
    this._queue.splice(0, 1)
    return value
  }
}
```

## 模块

- 使用标准的<font color="#e96900">ES6 </font> 模块语法 <font color="#e96900">import</font> 和 <font color="#e96900">export </font>

```js
// bad
const util = require('./util')
module.exports = util

// good
import Util from './util'
export default Util

// better
import { Util } from './util'
export default Util
```

- 不要使用 <font color="#e96900">import</font> 的通配符<font color="#e96900">\*</font> ，这样可以确保你只有一个默认的 <font color="#e96900">export</font>

```js
// bad
import * as Util from './util';

// good
import Util from './util';
```

## 对象属性

- 使用 <font color="#e96900">.</font> 来访问对象属性

```js
const joke = {
  name: 'haha',
  age: 28
};

// bad
const name = joke['name'];

// good
const name = joke.name;
```

## 标准特性

为了代码的可移植性和兼容性，我们应该最大化的使用标准方法，例如优先使用 <font color="#e96900">string.charAt(3)</font> 而不是 <font color="#e96900">string[3]</font>

## eval()

由于<font color="#e96900">eval</font> 方法比较<font color="#e96900">evil</font> ，所以我们约定禁止使用该方法

# vue 规范

参考官方风格指南，具体请访问[风格指南](https://www.w3cschool.cn/wematy/wematy-x9ne3bt0.html)

## 组件名为多个单词

<b>组件名应该始终是多个单词的，根组件 <font color="#e96900">App</font> 以及 <font color="#e96900">
&lt; transition &#62; </font> 、<font color="#e96900"> &lt; component &#62; </font> 之类的 <font color="#e96900">Vue</font> 内置组件除外。</b>

<br />这样做可以避免跟现有的以及未来的 <font color="#e96900">HTML</font> 元素相冲突，因为所有的 <font color="#e96900">HTML</font> 元素名称都是单个单词的。

```js
//bad
Vue.component('todo', {
  // ...
})
export default {
  name: 'Todo',
  // ...
}

//good
Vue.component('todo-item', {
  // ...
})
export default {
  name: 'TodoItem',
  // ...
}
```

## 组件数据

<b>组件的<font color="#e96900"> data </font> 必须是一个函数。</b>
当在组件中使用 <font color="#e96900"> data </font> property 的时候 (除了 <font color="#e96900"> new Vue </font> 外的任何地方)，它的值必须是返回一个对象的函数。

```js
//bad
Vue.component('some-comp', {
  data: {
    foo: 'bar'
  }
})
export default {
  data: {
    foo: 'bar'
  }
}

//good
Vue.component('some-comp', {
  data: function () {
    return {
      foo: 'bar'
    }
  }
})
// In a .vue file
export default {
  data () {
    return {
      foo: 'bar'
    }
  }
}
// 在一个 Vue 的根实例上直接使用对象是可以的，
// 因为只存在一个这样的实例。
new Vue({
  data: {
    foo: 'bar'
  }
})
```

## 为 <font color="#e96900"> v-for </font> 设置键值

<b>总是用 <font color="#e96900"> key </font> 配合<font color="#e96900"> v-for </font> 。 </b>
</br>在组件上总是必须用 key 配合 v-for，以便维护内部组件及其子树的状态。甚至在元素上维护可预测的行为，比如动画中的对象固化 (object constancy)，也是一种好的做法。

```js
//bad
<ul>
  <li v-for="todo in todos">
    {{ todo.text }}
  </li>
</ul>

//good
<ul>
  <li
    v-for="todo in todos"
    :key="todo.id"
  >
    {{ todo.text }}
  </li>
</ul>
```

## 单文件组件文件名的大小写

<b>单文件组件的文件名应该要么始终是单词大写开头 (PascalCase)，要么始终是横线连接 (kebab-case)。 </b>

```js
//bad
components/
|- mycomponent.vue
components/
|- myComponent.vue

//good
components/
|- MyComponent.vue (团队采用)
components/
|- my-component.vue
```

## 基础组件名

<b>应用特定样式和约定的基础组件 (也就是展示类的、无逻辑的或无状态的组件) 应该全部以一个特定的前缀开头，比如 <font color="#e96900"> Base </font>、<font color="#e96900"> App</font> 或<font color="#e96900">V </font> 。</b>

```js
//bad
components/
|- MyButton.vue
|- VueTable.vue
|- Icon.vue

//good
components/
|- BaseButton.vue
|- BaseTable.vue
|- BaseIcon.vue
components/
|- AppButton.vue
|- AppTable.vue
|- AppIcon.vue
components/
|- VButton.vue
|- VTable.vue
|- VIcon.vue
```

## 组件名中的单词顺序

<b>组件名应该以高级别的 (通常是一般化描述的) 单词开头，以描述性的修饰词结尾。 </b>

```js
//bad
components/
|- ClearSearchButton.vue
|- ExcludeFromSearchInput.vue
|- LaunchOnStartupCheckbox.vue
|- RunSearchButton.vue
|- SearchInput.vue
|- TermsCheckbox.vue

//good
components/
|- SearchButtonClear.vue
|- SearchButtonRun.vue
|- SearchInputQuery.vue
|- SearchInputExcludeGlob.vue
|- SettingsCheckboxTerms.vue
|- SettingsCheckboxLaunchOnStartup.vue
```

## 自闭合组件

<b>在单文件组件、字符串模板和 JSX 中没有内容的组件应该是自闭合的——但在 DOM 模板里永远不要这样做。 </b>

<br/>自闭合组件表示它们不仅没有内容，而且刻意没有内容。其不同之处就好像书上的一页白纸对比贴有“本页有意留白”标签的白纸。而且没有了额外的闭合标签，你的代码也更简洁。

不幸的是，HTML 并不支持自闭合的自定义元素——只有官方的“空”元素。所以上述策略仅适用于进入 DOM 之前 Vue 的模板编译器能够触达的地方，然后再产出符合 DOM 规范的 HTML。

```js
//bad
<!-- 在单文件组件、字符串模板和 JSX 中 -->
<MyComponent></MyComponent>
<!-- 在 DOM 模板中 -->
<my-component/>

//good
<!-- 在单文件组件、字符串模板和 JSX 中 -->
<MyComponent/>
<!-- 在 DOM 模板中 -->
<my-component></my-component>
```

## 完整单词的组件名

<b> 组件名应该倾向于完整单词而不是缩写。</b>
<br/>编辑器中的自动补全已经让书写长命名的代价非常之低了，而其带来的明确性却是非常宝贵的。不常用的缩写尤其应该避免。

```js
//bad
components/
|- SdSettings.vue
|- UProfOpts.vue

//good
components/
|- StudentDashboardSettings.vue
|- UserProfileOptions.vue
```

## scoped 中的元素选择器

<b>元素选择器应该避免在<font color="#e96900">scoped </font> 中出现。</b>
</br> 在 <font color="#e96900">scoped </font> 样式中，类选择器比元素选择器更好，因为大量使用元素选择器是很慢的。

```vue
//bad
<template>
  <button>X</button>
</template>

<style scoped>
button {
  background-color: red;
}
</style>

//good
<template>
  <button class="btn btn-close">X</button>
</template>

<style scoped>
.btn-close {
  background-color: red;
}
</style>
```

## 组件封装

组件封装的 props 需要返回默认值，说明传递参数

```js
 props: {
    propValue: {
      type: Object,
      default: () => {
        return {
          sliderTime: 3, //轮播时长
          resource: [
            {
              imgData: '', //图片地址
              title: '', //图片title
              linkType: 0, //链接类型
              url: '', //跳转地址
            },
          ],
        };
      },
    },
  },
```

# 图片规范

参考 W3Cschool,具体请访问 [W3Cschool](https://v2.cn.vuejs.org/v2/style-guide/index.html#%E4%BC%98%E5%85%88%E7%BA%A7-A%EF%BC%9A%E5%BF%85%E8%A6%81%E7%9A%84)

## 使用

[图片引入](https://blog.csdn.net/Start2019/article/details/120074411) 静态资源可以通过两种方式进行处理：</br>
在 JavaScript 被导入或在 template/CSS 中通过相对路径被引用。这类引用会被 webpack 处理。</br>
放置在 public 目录下或通过绝对路径被引用。这类资源将会直接被拷贝，而不会经过 webpack 的处理。</br>
所以会导致打包后图片丢失情况，团队约定以<font color="#e96900">@</font> 形式引入

```js
url('@/assets/resources/切图/bg.png')
require('@/assets/resources/categories/c1-1.png'),
```

## 团队约定

### 内容图

内容图多以商品图等照片类图片形式存在，颜色较为丰富，文件体积较大

- 优先考虑 <font color="#e96900">JPEG</font> 格式，条件允许的话优先考虑 <font color="#e96900">WebP</font> 格式
- 尽量不使用 <font color="#e96900">PNG </font>格式，<font color="#e96900">PNG8</font> 色位太低，<font color="#e96900">PNG24</font> 压缩率低，文件体积大

### 背景图

背景图多为图标等颜色比较简单、文件体积不大、起修饰作用的图片

- <font color="#e96900">PNG</font> 与 <font color="#e96900">GIF</font> 格式，优先考虑使用 <font color="#e96900">PNG </font>格式,<font color="#e96900">PNG </font>格式允许更多的颜色并提供更好的压缩率
- 图像颜色比较简单的，如纯色块线条图标，优先考虑使用 <font color="#e96900">PNG8 </font>格式，避免不使用 <font color="#e96900">JPEG</font> 格式
- 图像颜色丰富而且图片文件不太大的（<font color="#e96900">40KB</font> 以下）或有半透明效果的优先考虑 <font color="#e96900">PNG24</font> 格式
- 图像颜色丰富而且文件比较大的（<font color="#e96900">40KB</font> - <font color="#e96900">200KB</font>）优先考虑<font color="#e96900">JPEG </font> 格式
- 条件允许的，优先考虑 <font color="#e96900">WebP </font>代替<font color="#e96900">PNG</font> 和 <font color="#e96900">JPEG</font> 格式

```

```
