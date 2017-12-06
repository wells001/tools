# webpack

## webpack.dev.config.js

	const devWebpackConfig = merge(baseWebpackConfig, {
		devServer {
			// ...
			disableHostCheck: true, // 域名限制时添加可解决
			// ...
		}
	}