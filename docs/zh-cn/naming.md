# 命名规范

# 项目命名

全部采用小写方式， 以下划线分隔。 例：

```
my_project_name
```

# 目录命名

参照项目命名规则；
有复数结构时，要采用复数命名法。
例：

```
scripts，styles，images，data_models
```

# 组件命名

vue 的项目中，components 下的组件目录名，使用大驼峰命令
例：

```
LeftBar
```

# JS 文件命名

参照项目命名规则。
例：

```
account_model.js
```

# 变量命名

当命名变量时，主流分为驼峰式命名（variableName）和下划线命名（variable_name）两大阵营。

> 团队约定使用驼峰式命名

# CSS, SCSS 文件命名

参照项目命名规则。
例：

```
retina_sprites.css
```

# HTML 文件命名

参照项目命名规则。
例：

```
error_log.html
```

# 图片命名

图片命名建议以以下顺序命名

**图片业务（可选） +（mod\_）图片功能类别（必选）+ 图片模块名称（可选） + 图片精度（可选）**

1. 图片业务：

   - pp\*：拍拍
   - wx\*：微信
   - sq\*：手 Q
   - jd\*：京东商城
   - …

2. 图片功能类别：

   - mod\_：是否公共，可选
   - icon：模块类固化的图标
   - logo：LOGO 类
   - spr：单页面各种元素合并集合
   - btn：按钮
   - bg：可平铺或者大背景
   - …

3. 图片模块名称：

   - goodslist：商品列表
   - goodsinfo：商品信息
   - userava tar：用户头像
   - …

4. 图片精度：

   - 普清：@1x
   - Retina：@2x | @3x
   - …
     如下面例子：

```
公共模块：
wx_mod_btn_goodlist@2x.png
wx_mod_btn_goodlist.png
mod_btn_goodlist.png

非公共模块：
wx_btn_goodlist@2x.png
wx_btn_goodlist.png
btn_goodlist.png
```

# className 命名规范

参考 W3Cschool,具体请访问 [W3Cschool](https://www.w3cschool.cn/wematy/wematy-x9ne3bt0.html)

### 命名原则

基于姓氏命名法（继承 + 外来），祖先模块不能出现下划线，除了是全站公用模块，如 mod\_ 系列的命名：

```
<div class="modulename">
	<div class="modulename_info">
		<div class="modulename_son"></div>
		<div class="modulename_son"></div>
		...
	</div>
</div>

<!-- 这个是全站公用模块，祖先模块允许直接出现下划线 -->
<div class="mod_info">
	<div class="mod_info_son"></div>
	<div class="mod_info_son"></div>
	...
</div>
```

当子孙模块超过 4 级或以上的时候，可以考虑在祖先模块内具有识辨性的独立缩写作为新的子孙模块

```
<div class="modulename">
	<div class="modulename_cover"></div>
	<div class="modulename_info">
    	<div class="modulename_info_user">
    		<div class="modulename_info_user_img">
    			<img src="" alt="">
    			<!-- 这个时候 miui 为 modulename_info_user_img 首字母缩写-->
    			<div class="miui_tit"></div>
    			<div class="miui_txt"></div>
    			...
    		</div>
    	</div>
    	<div class="modulename_info_list"></div>
	</div>
</div>
```

### 模块命名

全站公共模块：以 ​mod_​ 开头

```
<div class="mod_yours"></div>
```

业务公共模块：以 业务名 ​*mod*​ 开头

```
<div class="paipai_mod_yours"></div>
```
