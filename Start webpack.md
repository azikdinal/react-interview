1) init project
```
npm init -y


```
2) create source folder for index
```
   src 
	   index.html
	   index.js
```
3) write the following text in cli
```
npm i -D webpack webpack-cli
```
4) in project folder create `webpack.config.js` file 
```javascript
const path = require("path")
const {CleanWebpackPlugin} = require("clean-webpack-plugin")
module.exports = {
	mode: "development",
	entry: "src/index.js",
	output:{
		path:path.resolve(__dirname, 'dist'),
		filename:"[name].[hash].js"
	},
	devServer:{
		port: 3000
	}
	plugins:[
		new HTMLWebpackPlugin({template:".src/index.html"})
		new CleanWebpackPlugin()
	],
	module:{
		rules:[{
			test:/\.(css|less)$/,
			use: ["style-loader", "css-loader", "less-loader"]
		},
		{
			test: /\.(jpg|jpeg|png|svg)/,
			use: ['file-loader']
		}
		]
	}
	
}
```
5) in cli `npm i -D style-loader less-loader css-loader file-loader html-webpack-plugin clean-webpack-plugin`
6) check app working right by running `webpack` in cli. 
   There should appear a folder in project dir named `dist`. That's your packed app.
7) in cli write `npm i -D webpack-dev-server`
8) to check `.less` files is working 
	1) in `/src` create `index.less` and use some styles.
	2) in `/src/index.js` write `import `./index.less`
	3) Pack app and check result
9) in `package.json` create new script `"start":"webpack-dev-server --open"`
10) check this: run in cli `npm run start`

#webpack 