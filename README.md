# AutoWebPlugin插件demo

> 在原demo的基础上添加了热替换功能

## Build Setup

``` bash
# install dependencies
npm install

# or

npm install --registry=https://registry.npm.taobao.org

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

执行`npm start`后，访问

`localhost:8080/login.html`

或

`localhost:8080/index.html`

## 问题解决

项目clone下来第一次执行`npm start`或`npm run dev`时会报错，只要删除`node_modules`文件夹下的`.3.8.1@webpack`文件后就可以正常运行了。

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
