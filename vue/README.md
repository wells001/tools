#关于vue的坑
 
## config 

### index.js

````
var path = require('path')

module.exports = {
	build: { // production 环境
		env: require('./prod.env'), // 使用 config/prod.env.js 中定义的编译环境
		index: path.resolve(__dirname, '../dist/index.html'), // 编译输入的 index.html 文件
		assetsRoot: path.resolve(__dirname, '../dist'), // 编译输出的静态资源路径
		assetsSubDirectory: 'static', // 编译输出的二级目录
		assetsPublicPath: '/', // 编译发布的根目录，可配置为资源服务器域名或 CDN 域名
		productionSourceMap: true, // 是否开启生产环境的 SourceMap
		// 开启后可以在浏览器 source -> webpack 目录中查看源代码 
		// Gzip off by default as many popular static hosts such as
		// Surge or Netlify already gzip all static assets for you.
		// Before setting to `true`, make sure to:
		// npm install --save-dev compression-webpack-plugin
		productionGzip: false, // 是否开启 gzip
		productionGzipExtensions: ['js', 'css'] // 需要使用 gzip 压缩的文件扩展名
	},
	dev: { // dev 环境
		env: require('./dev.env'), // 使用 config/dev.env.js 中定义的编译环境
		port: 8080, // 运行测试页面的端口
		assetsSubDirectory: 'static', // 编译输出的二级目录
		assetsPublicPath: '/', // 编译发布的根目录，可配置为资源服务器域名或 CDN 域名
		proxyTable: {}, // 需要 proxyTable 代理的接口（可跨域）
		// CSS Sourcemaps off by default because relative paths are "buggy"
		// with this option, according to the CSS-Loader README
		// (https://github.com/webpack/css-loader#sourcemaps)
		// In our experience, they generally work as expected,
		// just be aware of this issue when enabling this option.
		cssSourceMap: false // 是否开启 cssSourceMap
	}
}
````
## build

### utils.js

````

exports.cssLoaders = function (options) {
	
	...
	
	function generateLoaders(loader, loaderOptions) {
		
		...
		
		if (options.extract) {
			return ExtractTextPlugin.extract({
				use: loaders,
				fallback: 'vue-style-loader',
				publicPath : '../../', // 打包后发现文件路径错误可以尝试修改成此方式
			})
		} else {
			return ['vue-style-loader'].concat(loaders)
		}
		
		...
		
	}
	
	...
	
});
````


# webpack

## webpack.dev.config.js

	const devWebpackConfig = merge(baseWebpackConfig, {
		devServer {
			// ...
			disableHostCheck: true, // 域名限制时添加可解决
			// ...
		}
	}


## webpack.base.conf.js
```
	module.exports = {
		context: path.resolve(__dirname, '../'),
		entry: {
			app: ['babel-polyfill','./src/main.js'] // npm install babel-polyfill --save; 并修改app入口文件配置
			// 解决ie等低版本浏览器 Promise undefined 问题
		},
		// ···
	}
```
