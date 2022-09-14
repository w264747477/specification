# 注释

# HTML 注释规范

## 单行注释

```
<!-- Comment Text -->
<div>...</div>
```

## 模块注释

```
<!-- S Comment Text A -->
<div class="mod_a">
    ...
</div>
<!-- E Comment Text A -->
```

## 嵌套模块注释

```
<!-- S Comment Text A -->
<div class="mod_a">

    <div class="mod_b">
        ...
    </div>
    <!-- /mod_b -->

    <div class="mod_c">
        ...
    </div>
    <!-- /mod_c -->

</div>
<!-- E Comment Text A -->
```

# Css 注释规范

参考 html 注释规范

# js 注释

## 函数注释

```js
/*方法说明
 *@method 方法名
 *@description 方法作用
 *@param{参数类型}参数名 参数说明
 *@return {返回值类型} 返回值说明
 */
```

## 模块注释

```js
/* 模块说明
 * @module 模块名
 */

/* 类说明
 * @class 类名
 * @constructor
 */
```

# 代码作者规范

```js
<!--
 *@name:accountInfo
 *@desc:账户信息
 *@author:xxx
 *@time:2021/12/01
-->
```

#
