# my-vue

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

#一点提示
在vue-loader.conf.js 中通过配置插件来实现 插件为postcss-px2rem-dpr
``` bash
#代码示例

var utils = require('./utils')
var config = require('../config')
var isProduction = process.env.NODE_ENV === 'production'

var px2remConfig = {
  baseDpr: 1,             // base device pixel ratio (default: 2)
  remUnit: 75,            // rem unit value (default: 75)
  remPrecision: 5,        // rem value precision (default: 6)
  forcePxComment: 'px',   // force px comment (default: `px`)
  keepComment: 'no',       // no transform value comment (default: `no`)
  shouldUseDprRule: function(rule){
    var list = ['font', 'font-size'];
    return list.some(function(item) {
      return item === rule.property;
    })
  },
  shouldIgnoreRule: function(rule) {
    return  /border/.test(rule.property);
  }
}

module.exports = {
  loaders: utils.cssLoaders({
    sourceMap: isProduction
      ? config.build.productionSourceMap
      : config.dev.cssSourceMap,
    extract: isProduction
  }),
  postcss: [
    require('postcss-px2rem-dpr')( px2remConfig )
  ]
}
