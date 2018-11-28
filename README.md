# appcan4.0 开发指导

[TOC]

### 一、创建项目

1. 在appcan IDE中创建新项目，保留config.xml，删除根目录下的所有其他文件

2. 从gitlab上下载开发指导项目(下面是内网地址)

   ```
   git clone http://192.168.102.9/appcan4.0/developerGuide.git
   ```

3. 将project-folder内的所有文件copy到appcan新建项目的根目录下



### 二、目录结构

    ├── appcan							appcan原文件夹
    │   ├── assets							
    │   ├── css
    │   ├── js
    │   └── icon.png
    ├── common							公共文件夹
    │   ├── components					 	 组件文件夹
    │   │   └── jas-components.js			 
    │   ├── css							 	公共css文件夹
    │   ├── images							公共图片文件夹
    │   └── js								公共方法文件夹
    │       └── jas-tools.js					 
    ├── lib								第三方库
    │   ├── f2								f2移动端图表库
    │   ├── font-awesome-4.7.0				  字体库
    │   ├── mint-ui							 样式库
    │   └── vue								 vue2.0
    ├── pages							页面文件夹，按模块创建子文件夹
    │   └── modules							模块文件夹
    ├── config.xml						apppcan配置文件
    ├── index.html						主页面
    ├── init.html						初始界面，用于创建数据库
    └── login.html						登录界面


### 三、架构一览

![](https://ws1.sinaimg.cn/large/005ScKMTly1fx8jz2a8dzj30i50f9t98.jpg)



### 四、JS操作

1. 使用vue2.0进行JS基础框架的搭建

   官方文档地址： [https://cn.vuejs.org/v2/guide/]

2. 基于vue创建自己的组件库

   提高代码复用性，便于管理，提高开发效率

   统一置于common/components文件夹下

3. 公共js方法的封装

   统一置于common/js文件夹下



### 五、UI布局

1. 引入viewport的meta标签

   ```html
   <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"> 
   ```

   宽高等单位使用vw（1vw大小为屏幕宽度大小的1%）， 字体单位、边距等使用px；

2. mint-ui框架
   ```html
   引入css
   <link rel="stylesheet" href="./lib/mint-ui/style.css"> 
   引入js
   <script src="./lib/mint-ui/index.js"></script>
   ```

    官方文档地址： [https://mint-ui.github.io/docs/#/zh-cn2]


### 六、页面结构

![](https://ws1.sinaimg.cn/large/0062G6WRly1fxnuycojsdj312s0o3q6l.jpg)

### 七、Demo示例

##### 1. 示例 login.html

1. vue实例的创建，vue配置项

2. mint-ui框架的使用， input和button组件，toast方法等

3. 组件的封装与使用，header组件

4. appcan请求数据

5. appcan 页面跳转

   

##### 2. 示例 index.html

1. vue指令的封装和使用，v-setheight自适应div高度

2. vue钩子，created方法介绍

3. vue配置项，watch的使用

4. mint-ui 中[tabbar](http://mint-ui.github.io/docs/#/zh-cn2/tabbar) 组件与appcan中popover的结合使用，(屏幕像素比)

5. appcan实体键监听方法

   


##### 3. 示例 pages/data-statistics/data-statistics.html

1. 移动端图表F2的使用，[官方文档](https://antv.alipay.com/zh-cn/f2/3.x/)

2. 自定义组件 jas-select-field ，下拉选组件

3. 自定义组件 jas-group ，分组组件

   


##### 4. 示例 pages/data-collection/form/form.html

1. 自定义组件 jas-form-items-group，表单项组件

2. 自定义组件 jas-file-group，附件组件（选取，上传，下载，图片预览功能）

3. 自定义组件 jas-button-footer，底部按钮组件

4. 跨页面传参，取值jasTools.base.getParamsInUrl() ，赋值jasTools.base.setParamsToUrl 

    

##### 5. 示例 pages/data-review/checkList/checkList.html

1. mintui中[mt-loadmore](http://mint-ui.github.io/docs/#/zh-cn2/loadmore)组件，上拉刷新，下拉加载的使用 
2. mintui中[mt-tab-container](http://mint-ui.github.io/docs/#/zh-cn2/tab-container)组件，子页面切换容器



##### 6. 功能 本地数据库操作

数据库操作通用方法 data-base-operation.js 

1. 多表的快速创建

   示例：init.html

2. 数据库的增删改查

   示例：pages/user-center/data-sync/data-sync-main.html







​      