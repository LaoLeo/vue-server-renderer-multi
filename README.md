# vue-server-renderer-multi

在vue-server-renderer插件基础上改造，支持可配置多入口，demo参看请点击[这里](https://github.com/LaoLeo/multi-pages-vue-ssr#readme)

## 解决的问题

假如你的应用中包含了项目首页（A）和后台系统（B）两种相关性不强的页面，但因为都用到共用组件而不好分离。由于vue-server-renderer不能配置多入口的限制（配置多多入口打包server bundle会报错），那么渲染出来的html中的资源文件会是AB两种页面所需资源的混合，可能A页面加载了只有B页面才用到的资源，这正是这个项目需要解决的问题。

## 功能
在vue-server-renderer原有能力上做了更改和扩展了以下的几点能力：

- client-plugin输出的client manifest文件中的initial值按入口划分
- server-plugin支持配置多入口
- 根据入口渲染需要的preload和prefetch的资源


## 结构预览

<img width="973" alt="screen shot" src="http://m.qpic.cn/psc?/V12x89qA2LlAEO/45NBuzDIW489QBoVep5mcQyMcBQttO*WSkcLH5bz9IY8Jl8FscABxn7MhaRhIckDJDjLNeIFS*xL93bPNT3cNR8H9wKQDbFqL14fW1e4dTg!/b&bo=*APMAfwDzAEDFzI!&rf=viewer_4">

