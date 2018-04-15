# 微信小程序开发最佳实践

## WeChat Mini Program Development Best Practices

[![文档完善中](https://img.shields.io/badge/当前状态-文档完善中-red.svg?style=for-the-badge)](https://github.com/gaomd/wechat-mini-program-dev-best-practices)
[![Work in Progress](https://img.shields.io/badge/STATUS-Work_in_Progress-red.svg?style=for-the-badge)](https://github.com/gaomd/wechat-mini-program-dev-best-practices)

本文作者结合微信小程序实际开发经验，精心整理了本篇最佳开发实践，旨在帮助读者避开小程序的坑，快速上手，高效开发。

> 本文使用中文撰写，但文中链接大多指向英语原版文档，故要求读者具备一定的英语阅读能力，读者亦可自行寻找对应的中文文档。

## 准备

首先划重点：`微信小程序 === 前端开发`，没错：`微信小程序 === 前端开发`。

因此读者需要掌握基本的前端技能 HTML、CSS 和 JavaScript（ES6+）。

此外，我们将直接放弃微信官方的小程序开发方式，转而使用美团点评的小程序开发框架：[mpvue](https://github.com/Meituan-Dianping/mpvue)，其最大的优势在于底层使用修改过的 Vue.js 核心，并采用 `*.vue` 单文件组件化开发方式，再通过 webpack 的强大构建能力，体面地将开发代码转化为小程序代码。

<!-- Vue.js 的数据双向绑定、组件化等特性将极大提高开发效率。 -->

所以，我们的开发技术栈就成型了。

#### 必备技能：

0. 英语
1. HTML
2. CSS
3. JavaScript（[ES6+](https://github.com/lukehoban/es6features)）
4. [Vue.js](https://vuejs.org/v2/guide/) & [mpvue](http://mpvue.com/)
5. 微信
    * [小程序文档（别忘了读「开发-API」章节）](https://developers.weixin.qq.com/miniprogram/introduction/index.html)
    * [WeUI 样式库](https://github.com/Tencent/weui-wxss/)
6. Node.js：掌握 `npm (un)install` 即可

#### 可选技能（按照重要度排序）：

* HTML: [Semantic 语义化](https://en.wikipedia.org/wiki/Semantic_HTML)
* CSS: [Airbnb CSS / Sass Style Guide](https://github.com/airbnb/css)
* CSS: OOCSS & [BEM](http://getbem.com/introduction/) & [Namespacing](https://www.smashingmagazine.com/2016/06/battling-bem-extended-edition-common-problems-and-how-to-avoid-them/#2-should-i-be-namespacing)
* CSS: [Sass（SCSS）](https://sass-lang.com/guide)
* CSS: [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* JavaScript: [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
* Vue.js: [Vuex](https://vuex.vuejs.org/en/)
* Node.js: webpack 构建工具
* Node.js: ESLint 代码风格检测工具
* Node.js: stylelint 样式风格检测工具

#### 拓展了解技能：

* Sketch
* [Bootstrap 4](https://getbootstrap.com/)
* RESTful API
* JSON Web Token
* OAuth 2.0
* 微信: [JavaScript SDK（JS-SDK）](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421141115)

掌握以上必备技能，我们进入开发。

## 发布

小程序的发布分为三个阶段：

0. 在 IDE 中上传开发版本，此时需设置版本号和可选的描述信息，上传后【后台】可见
1. 开发版本，将该版本设为体验版后即可提供给试用成员，在 IDE 中上传新版本会覆盖当前版本
2. 审核版本，在提交审核时可为每个页面填写 16 个汉字标题和 10 个关键词的 SEO 信息，认真对待这个机会
3. 线上版本，恭喜

### 体验版

在【后台】-【用户身份】-【成员管理】中添加体验成员才能使其拥有体验权限。

### 版本号

小程序对版本号有严格要求，只能使用数字、字母和 `.` 三类字符，且总长度限制为 10 个字符。

推荐以下版本号规则：

* 预览版：`[MAJOR].[MINOR].[PATCH]p[PREVIEW]`
* 送审版：`[MAJOR].[MINOR].[PATCH]r[REVIEW]`

例如 `1.0.0p2` 代表即将发布的 `1.0.0` 版的第二个体验版，而 `1.0.0r1` 代表 `1.0.0` 版的第一个送审版，审核成功后该版本即成为最终版本号。

## License

![Creative Commons License](https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png)

Copyright (c) 2018 Mengdi Gao

本作品采用[知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh)进行许可。

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).
