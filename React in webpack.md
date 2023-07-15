1) install `babel` to project using cli `npm i -D babel-loader @babel/core`
2) add to `/webpack.config.js` new `rule`
```javascript
{  
	test: /\.m?js$/,  
	exclude: /node_modules/,  
	use: {  
	loader: "babel-loader",  
	options: {  
		presets: ['@babel/preset-env']  
			}  
	}  
}
```
3) write `npm i @babel/preset-env -D`
4) to enable `React` and `.jsx` write `npm i -D @babel/preset-react`
5) write new rule
```javascript
{  
	test: /\.m?jsx$/,  
	exclude: /node_modules/,  
	use: {  
	loader: "babel-loader",  
	options: {  
		presets: ['@babel/preset-env', "@babel/preset-react"]  
			}  
	}  
}
```
6) change `entry` in `webpack.config.js` to `["./src/index.jsx"]`
7) write `npm i --save @babel/polyfill`
8) add to `entry` `"@babel/polyfill"`
9) rename `index.js` to `.jsx`
10) `npm i react react-dom`
11) add folder `/src/components`

Note: you need to use `.jsx` when to import component files

#webpack #react 