## 项目简介
使用方式：<br>
确保数据库文件已导入<br>
git bash运行以下命令：<br>
（前端文件夹中）git clone https://github.com/Huborun/-MiMall.git<br>
（后端文件夹中）git clone https://github.com/Huborun/MiMallBackstage.git<br>
若git clone出错，则使用<br>
git config --global http.sslVerify "false"<br>
和git config --global --unset http.proxy<br>
在Vscode中分别打开这两个文件<br>
对于前端文件，使用：<br>
npm clean-install<br>
cnpm i<br>
npm run serve<br>
对于后端文件，使用：<br>
npm clean-install<br>
cnpm i<br>
npm run start<br>
之后打开http://localhost:6789/#/index即可<br>
### 项目名
项目名：小米商城复刻实现1.0<br>
项目实现方式：前端使用Vue，后端使用Node和Express框架，数据库使用Mysql。<br>

### 注意事项
分辨率：**2560 X 1440**<br>
浏览器：**谷歌浏览器**<br>

### 主要使用工具版本
MySQL：版本8.0.19<br>
vue/cli：版本4.5.15<br>
vue-router: 3.5.3<br>
vuex: 3.6.2<br>
SCSS: 1.43.4<br>
Node：版本14.17.3<br>
Express：版本4.16.1<br>
图标字体：阿里巴巴的图标字体<br>

## 实现内容<br>
1.小米商城首页（几乎1:1实现）<br>
2.小米商城登录功能，以及对错误输入的处理（暂不能注册）<br>
3.小米商城的购物车及购物车的相关功能（全选反选、增加减少商品数量、删除商品、购买限额）<br>
4.小米商城商品查看（5个商品：小米MIX4、MIX FOLD、小米11Ultra、红米K40、红米Note11Pro）<br>
5.小米商城商品加购界面<br>
6.加购成功页面<br>
7.下订单页面（收货地址的增加及修改）<br>
8.下订单成功页面<br>
9.订单页面（不能购买成功，因为我没有买过东西）<br>
10.订单详情页面<br>
## 实现方式
### Vue/JS使用
Promise/axios:大量，以获取数据，并向服务器发送请求操作数据库，实现对商品、购物车、订单、地址的增删改查<br>
DOM操作：大量，因为JQuery多次安装均失败，所以均使用原生DOM操作<br>
Vue的混入：将处理字符串、提交操作、购物车新增操作的方法提取到混入js文件中<br>
cookies：判断用户是否已登录并保证**刷新后**依然能获取数据<br>
Vuex：存储用户的购物车、订单信息并获取，每次操作购物车、订单都会提交修改以保持最新<br>
父组件通过props向子组件发送信息：大量<br>
父组件使用refs调用子组件的方法：购物车页面全选反选的实现<br>
组件自定义事件/事件总线：购物车页面全选反选的实现；获取用户输入的地址<br>
Vue路由传参：较多<br>
Vue嵌套路由：home组件及order组件<br>
Vue的组件路由守卫：加购页面获取商品信息<br>
Vue的全局后置路由守卫：设置当前页面的title<br>
### Node/Express使用
查询操作：查询首页大量广告的相关信息、查询那5个手机的相关信息；查询用户的购物车信息、订单信息、地址信息<br>
增加操作：新增用户购物车信息、新增用户地址、新增用户订单<br>
修改操作：修改用户购物车商品数量、修改用户地址<br>
删除操作：删除单个用户购物车信息（注：小米做的小米商城中，是不可以删除用户地址的）<br>
