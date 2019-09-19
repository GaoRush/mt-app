# mt-app

> study

## Build Setup

``` bash
# install dependencies
$ npm run install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

<!-- 
*****项目安装流程*****
1.npm install -g npx
2.npx create-nuxt-app project-name
3.解决不支持import '' from ''语法：
3.1 package.json的"scripts"里的编译模式"dev" 和"start"添加"--exec babel-node"：
  "scripts": {
    "dev": "cross-env NODE_ENV=development nodemon server/index.js --watch server --exec babel-node",
    "build": "nuxt build",
    "start": "cross-env NODE_ENV=production node server/index.js --exec babel-node",
    "generate": "nuxt generate"
  }
3.2 安装npm i -g babel-cli ，npm i -D babel-preset-env（babel-preset-2015已被弃用），项目根目录下创建babel的配置文件".babelrc"，输入：
{
  "presets": ["env"]
}

4.解决不支持sass：
npm i -D sass-loader node-sass

5.mongoDB 数据库安装

6.Redis 数据库安装

7.Robo 3T  数据库可视化软件安装

8.npm 包安装
npm i -D koa-router koa-redis nodemailer axios koa-passport passport-local koa-bodyparser koa-generic-session koa-json mongoose crypto-js

9.需要开启mongod服务，redis数据库：
$ mongod --dbpath="D:\Program Files\MongoDB\data\db"
$ ./redis-server
-->