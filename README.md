
## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```
****

## 特别说明
1. 开发中要设置启动的端口，去server/index.js文件修改host和port的参数；
2. 开发中接口设置， 去plugins/axios.js里面修改baseURL
3. 全球化基础数据在publice/lang下面文件修改
4. 该架构无需设置路由，只需要在pages文件下创建.vue文件会自动生成路由。规则请参照https://zh.nuxtjs.org/guide/routing
5. layouts文件为布局方式，默认是使用default.vue的布局，如需自定义就在此文件定义布局，然后再pages下的文件中添加一个属性layout: '你要的布局文件名称',该数据与vue的data是同级别的。

