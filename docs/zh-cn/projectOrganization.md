# 项目组织规范

以 vue 项目为列:

```js
.
├── Docker(打包)
│   ├── Dockerfile
│   ├── nginx.conf
├── public(全局资源，放入src可能访问不到)
│   ├── favicon.ico
│   ├── index.html
├── src(项目相关)
│   ├── App.vue
│   ├── assets
│   │   ├── images（图片）
│   │   │   ├── BG.png
│   │   ├── libs (第三方类库)
│   │   │   ├── day.js
│   │   ├── fonts (字体)
│   │   │   ├── demo.css
│   │   │   ├── demo_index.html
│   │   │   ├── iconfont.css
│   │   │   ├── iconfont.js
│   │   │   ├── iconfont.json
│   │   │   ├── iconfont.ttf
│   │   │   ├── iconfont.woff
│   │   │   └── iconfont.woff2
│   │   ├── css（公共样式，全局样式）
│   │   │   ├── style.css
│   │   └── scss公共样式，全局样式）
│   │       └── variables.scss(定义变量值)
│   │       └── style.scss（基本样式，以及变量解析。样式书写，先参考此文件是否有该样式）
│   ├── components(公共组件)
│   │   └── gradientLine
│   │       └── index.tsx
│   ├── constant（自定义常量）
│   │   ├── uri.js(定义接口url)
│   │   └── returnCode.js(定义接口返回码表)
│   │   └── index.js(定义常量值)
│   │   └── localStorage.js(定义本地存储)
│   ├── main.ts
│   ├── router(路由)
│   │   └── index.ts
│   ├── store（vuex状态管理，项目复杂，需要分包）
│   │   ├── index.ts
│   │   └── moduleA
│   │       ├── mapInfo.ts
│   │   └── moduleB
│   │       ├── mapInfo.ts
│   ├── utils（实用工具类）
│   │   ├── axios.ts
│   │   ├── index.ts
│   └── views(视图)
│       ├── page1(页面)
│       │   ├── components(页面内部组件)
│       │   │   ├── arrowbox
│       │   │   │   └── index.vue
│       │   │   └── circleNum
│       │   │       └── index.vue
│       │   └── index.vue
├── vue.config.js（vue配置）
├── babel.config.js(babel配置)
├── .prettierrc.js(根据配置保存时格式化代码)
├── .eslintrc.js(代码规范)
├── package-lock.json
├── package.json
├── yarn-error.log
└── yarn.lock
├── .env
├── .env.development
├── .env.production
└── .env.test
├── LICENSE（项目信息）
├── README.md(项目文档)
```
