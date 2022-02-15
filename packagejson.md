```javascript
某些项目依赖对应插件
{
  "name": "admin-app",
  "version": "1.0.0",
  "author": "chuzhixin",
  "license": "Mozilla Public License Version 2.0",
  "private": true,
  "participants": [
    "fwfmiao"
  ],
  "homepage": "https://chu1204505056.gitee.io/admin-app",
  "scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build",
    "build:report": "vue-cli-service build --report",
    "lint": "vue-cli-service lint",
    "lint:style": "stylelint **/*.{vue,scss} --fix",
    "inspect": "vue-cli-service inspect",
    "template": "plop",
    "clear": "npm cache clean -f&&rimraf node_modules&&npm install --registry=https://registry.npm.taobao.org&&cnpm i image-webpack-loader -D",
    "use:npm": "nrm use npm",
    "use:taobao": "nrm use taobao",
    "update": "ncu -u --registry https://registry.npm.taobao.org&&npm install --registry=https://registry.npm.taobao.org&&cnpm i image-webpack-loader -D",
    "update:globle": "ncu -g",
    "push": "start ./push.sh",
    "deploy": "start ./deploy.sh",
    "docker:build": "npm run build&&docker build --pull --rm -f \"dockerfile\" -t vueadminbeautifulpro:latest \".\"&&docker run --rm -d  -p 80:80/tcp vueadminbeautifulpro:latest",
    "image-webpack-loader": "cnpm i image-webpack-loader -D"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/vue-admin-beautiful/admin-app.git"
  },
  "dependencies": {
    "@riophae/vue-treeselect": "^0.4.0",
    "@turf/turf": "^6.3.0",
    "axios": "^0.21.1",
        // axios 网络通信
    "clipboard": "^2.0.6",
    "colorette": "^1.2.1",
    "core-js": "^3.8.3",
    "dayjs": "^1.10.4",
        // 对时间进行处理的js库
    "echarts": "^5.0.1",
        // 表单库
    "element-ui": "^2.15.0",
        // ui组件
    "eslint-loader": "^4.0.2",
        // 语法检查
    "file-loader": "^4.3.0",
    "file-saver": "^2.0.5",
    "jquery": "^3.5.1",
        // jq
    "js-cookie": "^2.2.1",
    "jsencrypt": "^3.0.0-rc.1",
    "jsplumb": "^2.15.5",
    "jsts": "^2.5.0",
    "lodash": "^4.17.20",
    "mockjs": "^1.1.0",
        // 本地端口模拟调试
    "nprogress": "^0.2.0",
    "ol": "^6.5.0",
    "ol-contextmenu": "^4.1.0",
    "ol-ext": "^3.1.18",
    "ol-popup": "^4.0.0",
    "qs": "^6.9.6",
    "resize-detector": "^0.2.2",
    "screenfull": "^5.1.0",
        // vue 中的全屏插件,提供全屏放大功能
    "vab-icons": "0.0.15",
    "vue": "^2.6.12",
    "vue-clipboard2": "^0.3.1",
    "vue-i18n": "^8.22.4",
    "vue-pdf": "^4.2.0",
    "vue-router": "^3.5.1",
    "vuedraggable": "^2.24.3",
    "vuex": "^3.6.2",
    "vxe-table": "^3.1.6",
        // vxe-table 提供高级表单
    "xe-utils": "^3.1.8",
        // vxe-table 能够运行的依赖库
    "xlsx": "^0.16.9",
    "zx-markdown-editor": "^0.0.2"
  },
  "devDependencies": {
    "@vue/cli-plugin-babel": "^4.5.11",
    "@vue/cli-plugin-eslint": "^4.5.11",
    "@vue/cli-service": "^4.5.11",
    "@vue/eslint-config-prettier": "^6.0.0",
    "babel-eslint": "^8.2.6",
    "body-parser": "^1.19.0",
    "chalk": "^4.1.0",
    "chokidar": "^3.5.1",
    "compression-webpack-plugin": "^7.1.2",
    "eslint": "^4.19.1",
    "eslint-plugin-prettier": "^3.3.1",
    "eslint-plugin-vue": "^7.5.0",
    "filemanager-webpack-plugin": "^3.1.0",
    "image-webpack-loader": "^7.0.1",
    "lint-staged": "^10.5.3",
    "node-sass": "^6.0.0",
    "plop": "^2.7.4",
    "prettier": "^2.2.1",
    "raw-loader": "^4.0.2",
    "sass": "1.32.8",
    "sass-loader": "10.1.1",
    "stylelint": "^13.9.0",
    "stylelint-config-prettier": "^8.0.2",
    "stylelint-config-recess-order": "^2.3.0",
    "svg-sprite-loader": "^5.2.1",
    "vue-plugin-rely": "^2.6.12",
    "vue-template-compiler": "^2.6.12",
    "webpackbar": "^4.0.0",
    "zx-templates": "^0.0.26"
  },
  "gitHooks": {
    "pre-commit": "lint-staged"
  },
  "lint-staged": {
    "*.{js,jsx,vue}": [
      "vue-cli-service lint",
      "git add"
    ]
  },
  "keywords": [
    "vue",
    "admin",
    "dashboard",
    "element-ui",
    "vue-admin",
    "element-admin",
    "boilerplate",
    "admin-template",
    "management-system"
  ],
  "engines": {
    "node": ">=8.9",
    "npm": ">= 3.0.0"
  }
}

```

