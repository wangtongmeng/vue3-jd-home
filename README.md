# 京东到家webapp

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## vscode插件
- eslint
- vetur vue单文件 template下必须是单标签，vue3中不需要

## chrome插件
- vue.js devtools

## 基础样式集成及开发模拟器的使用
npm install normalize.css --save 固定版本 npm install normalize.css@8.0.1 --save
style中统一管理样式文件，并在main.js引入主文件
- index.scss
- base.scss
- iconfont.css 使用在线unicode形式
- viriables.scss 样式变量 颜色
- mixins.scss 样式片段 省略号
设置chrome控制台，在模拟器 iphone6下开发

BEM(block element Modifier) css命名规则  block_element--Modifier(表状态)  block 块
如何看待 CSS 中 BEM 的命名方式？  https://www.zhihu.com/question/21935157

组件style+scoped 避免样式冲突


## 登录校验
router.beforeEach 做登录校验
登录操作后，将记录登录标识isLogin在localStorage
如果没有登录,访问其他页面跳转login页，访问login/register页直接next()
如果已经登录，其他页面直接next()，访问login/register页跳转home页(也可配置在路由配置选项beforeEnter中)


## 小技巧

### 如何设置字体10px(chrome浏览器默认字体最小是12px)
```css
.title {
    font-size: 20px;
    transform: scale(.5, .5);
    transform-origin: center top;
}
```
### position:relative;经常用于微调位置
### 根据图片比例设置占位，防止图片加载完成前的塌陷问题
```scss
.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;
  &__img {
    width: 100%;
  }
}
```
## 依赖
- npm install axios normalize.css --save

## 封装axios

封装出post方法，基础路径 'Content-Type': 'application/json'，减少一层嵌套 res.data


## mock
fastmock
## 通用组件及复用组件
通用组件：Toast
复用组件：ShopInfo


通过代码拆分增加逻辑可维护性

## input不显示旧密码 autocomplete
```html
<input
    type="password"
    class="wrapper__input__content"
    placeholder="请输入密码"
    autocomplete="new-password"
    v-model="password"
/>
```


## 路由懒加载提高首屏加载速度

## rem

图片没有时，会显示缩略图的问题
1.设置默认图片 2.通过v-show v-if控制显隐，当url不加载时不显示图片