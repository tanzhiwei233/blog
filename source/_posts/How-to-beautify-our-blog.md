---
title: How to beautify our blog
date: 2025-06-26 17:42:33
tags: blog
---

1、install hexo according to the following documentation and initialize our blog

https://hexo.io/zh-cn/docs/

2、modify site config.yml to set the theme for our blog

```shell
git clone git@github.com:theme-next/hexo-theme-next.git themes/next
#cofig.yaml
theme: next
```

3、write the frist article

```shell
hexo new post "how to beautify our blog"
```

4、Execute the following command to start our website

```shell
hexo clean hexo g hexo s
```

Ok,if you are running your hexo  locally, your blog by visiting http://localhost:4000 in you web browser.

5、create some necessary pages and update theme config 'menu'
```shell
hexo new page tags
hexo new page categories
hexo new page about
```
6、add the effect of click love heart

create new file clicklove.js in /themes/next/source/js and implement the following code on js
```js
!function(e,t,a){function n(){c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"),o(),r()}function r(){for(var e=0;e<d.length;e++)d[e].alpha<=0?(t.body.removeChild(d[e].el),d.splice(e,1)):(d[e].y--,d[e].scale+=.004,d[e].alpha-=.013,d[e].el.style.cssText="left:"+d[e].x+"px;top:"+d[e].y+"px;opacity:"+d[e].alpha+";transform:scale("+d[e].scale+","+d[e].scale+") rotate(45deg);background:"+d[e].color+";z-index:99999");requestAnimationFrame(r)}function o(){var t="function"==typeof e.onclick&&e.onclick;e.onclick=function(e){t&&t(),i(e)}}function i(e){var a=t.createElement("div");a.className="heart",d.push({el:a,x:e.clientX-5,y:e.clientY-5,scale:1,alpha:1,color:s()}),t.body.appendChild(a)}function c(e){var a=t.createElement("style");a.type="text/css";try{a.appendChild(t.createTextNode(e))}catch(t){a.styleSheet.cssText=e}t.getElementsByTagName("head")[0].appendChild(a)}function s(){return"rgb("+~~(255*Math.random())+","+~~(255*Math.random())+","+~~(255*Math.random())+")"}var d=[];e.requestAnimationFrame=function(){return e.requestAnimationFrame||e.webkitRequestAnimationFrame||e.mozRequestAnimationFrame||e.oRequestAnimationFrame||e.msRequestAnimationFrame||function(e){setTimeout(e,1e3/60)}}(),n()}(window,document);
```
then implement the following code at the end of file \themes\next\layout\_layout.swig
```js
<!-- 页面点击小红心 --> <script type="text/javascript" src="/js/clicklove.js"></script>
```
7、modification of the website avatar and website favicon
put your favorite avatar and favicon under the folder of theme source,
find the avatar and  favicon in theme config,modify the url according your file name of avatar and favicon

8、open on-site search functionality

install plugin hexo-generator-searchdb
```shell
npm install hexo-generator-searchdb –save
```
add the following code on hexo config
```shell
#表示站内搜索
search:  
    path: search.xml
    field: post
    format: html
    limit: 10000
```
and modify the local_search on theme config

9、setup the animation background
refer to this project  `https://github.com/theme-next/theme-next-three`

10、deploy your blog on github

install plugin
```shell
npm install hexo-deployer-git --save
```
set hexo config
```shell
deploy:
  type: git
  repository: git@github.com:用户名/用户名.github.io.git
  branch: master
```
11、how to add live2d-widget

add the following code in next theme /layout/_layout.swig
```shell
<script src="https://fastly.jsdelivr.net/gh/stevenjoezhang/live2d-widget@latest/autoload.js"></script>
```
git clone git@github.com:tanzhiwei233/live2d-widget.git



