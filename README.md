# meituan_app

> My praiseworthy Nuxt.js project

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

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).

#在server中可以使用import语法
#1 "dev": "cross-env NODE_ENV=development nodemon server/index.js --watch server --exec babel-node",
# "start": "cross-env NODE_ENV=production node server/index.js --exec babel-node"

#2 创建.babelrc文件 
#{
#    "presets":["es2015"]
#}

#3安装-重启项目
#npm i babel-core babel-preset-es2015 babel-cli

#安装sass
#npm i sass-loader node-sass

