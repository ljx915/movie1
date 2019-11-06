# 电影项目

## 查看
- git pull + 项目地址 -> npm install ->npm run serve

## 文件目录树
```md
.
├── README.md
├── babel.config.js
├── package-lock.json
├── package.json
├── public (存放公共文件)
│   ├── css
│   │   └── reset.css
│   ├── favicon.ico
│   ├── font (字体图表文件)
│   │   ├── iconfont.eot
│   │   ├── iconfont.svg
│   │   ├── iconfont.ttf
│   │   ├── iconfont.woff
│   │   └── iconfont.woff2
│   └── index.html
├── src
│   ├── App.vue
│   ├── assets (存放一些图片等)
│   │   ├── CityHall.png
│   │   ├── lazy1.jpg
│   │   ├── max.png
│   │   ├── message.png
│   │   ├── movie.jpg
│   │   ├── movie.png
│   │   └── personal.png
│   ├── components(子组件)
│   │   ├── cityIndex
│   │   ├── footer
│   │   ├── header
│   │   ├── js
│   │   ├── loading
│   │   ├── movieIndex
│   │   ├── personIndex
│   │   └── scroller
│   ├── main.js（入口文件）
│   ├── routers (路由文件)
│   │   ├── city
│   │   ├── index.js
│   │   ├── movie
│   │   └── person
│   ├── stores (状态管理文件)
│   │   ├── city
│   │   └── index.js
│   └── views （主要示图文件）
│       ├── city
│       ├── movie
│       └── person
├── tree.md
└── vue.config.js
```

## 初始化项目 

- 手动配置的。配置的`vue-router`,`vuex`,`node-sass`,`eslint`..


<!-- ## 页面展示

<figure class="third">

<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p1.png?raw=true" width=200 height=400 alt="图1">
<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p2.png?raw=true" width=200 height=400 alt="图2">
<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p3.png?raw=true" width=200 height=400 alt="图3">

</figure>

<figure class="third">

<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p4.png?raw=true" width=200 height=400 alt="图4">
<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p5.png?raw=true" width=200 height=400 alt="图5">
<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p6.png?raw=true" width=200 height=400 alt="图6">

</figure>

<figure class="two">

<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p7.png?raw=true" width=200 height=400 alt="图7">
<img src="https://github.com/yaogengzhu/maioyan/blob/master/showImage/p8.png?raw=true" width=200 height=400 alt="图8">

</figure > -->



## 项目接口文件 
  | 接口名称 | 请求方式 | 请求示列 |
  | --- | ---- | ---- |
  | 正在热映 | get | http://39.97.33.178/api/movieOnInfoList?cityId=10 |
  | 即将上映 | get | http://39.97.33.178/api/movieComingList?cityId=10 |
  | 搜索 | get | http://39.97.33.178/api/searchList?cityId=10&kw=a |
  | 城市 | get | http://39.97.33.178/api/cityList |
  | 电影详情 | get | http://39.97.33.178/api/detailmovie?movieId=345808 |
  | 影院 | get | http://39.97.33.178/api/cinemaList?cityId=10 |
  | 城市定位 | get | http://39.97.33.178/api/getLocation |

## 技术要点
- [x] `vue`
- [x] `vuex`
- [x] `vue-router`
- [x] `better-scroll`
- [x] `proxy`
- [x] `axios`


## 项目结构分析
本次项目方式全部将采用子组件方式去创建，可以根据目录看到
- `views`文件作为视图层，作为三个大的单页面去实现
- `components` 文件存放自子组件，这些子组件的功能是一次书写，可以多次调用。比如`header`作为头部分的页面，不仅是在单个页面拥有，而且是在其他三个大的单页面同时拥有，这时候就被抽离出来，以便与随时调用。
- `routers` 对于路由组件来说，本来就存在一个`index.js`就已经足够使用，但是为了后续大的项目，本次页将抽离出来。每个页面的路由都抽离作为一个文件存放，以方便管理。
