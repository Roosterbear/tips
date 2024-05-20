# WEBPACK

## START

> mkdir project
>cd project
>npm init -y
>yarn add -D webpack
>mkdir src 

* Create a __index.js__ inside
* Add code: _console.log('Hi from webpack');_

>mkdir dist

* Create a __index.html__ inside
* Add basic HTML code

* In our project folder, create a: __webpack.config.js__ file
* Add:

```javascript
const path = require('path');
module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolver(__dirname, 'dist')
  }
}
```

* Add reference in our __index.html__

```html
<script src="bundle.js"></script>
```

* Edit __package.json__:

```json
"scripts":{
  "build":"webpack"
}
```

* Exec:

>yarn run build














## DEV SERVER

In a terminal, create a new folder to your project and hit enter. Then enter the folder. <br/>

```terminal
mkdir project
cd project
```

Create the _src_, _dist_, and _config_ folders. <br/>

```terminal
mkdir src dist config
```

Initialize git with the __.gitignore__ file and a the npm project: <br/>

```terminal
npm init -y
```

Now install __webpack__ and create start files:<br/>

```terminal
npm install -g webpack webpack-cli
touch src/index.js dist/index.html
```

Add code to _index.js_ like: alert("Hello world"); <br/>

---

__check development and production modes__ <br/>

```terminal
webpack --mode=development
```

Check the __main.js__. <br/>

```terminal
webpack --mode=production
```

Now check the _main.js_ __file size__ <br/>

---

__create webpack configuration file__ <br/>

```terminal
touch config/webpack.dev.js
rm dist/main.js src/index.js
```

__edit webpack configuration file__ <br/>

__CREATE__ the file: <br/>

```terminal
touch src/main.js
```

__edit config/webpack.dev.js__ <br/>

```javascript
const path = require("path")

module.exports = {
  entry:{
    main: "./src/main.js"
  },
  mode: "development",
  output: {
    filename: "[name]-bundle.js",
    path: path.resolve(__dirname, "../dist")
  }
}
```

__run config file:__ <br/>

```terminal
webpack --config=config/webpack.dev.js
```

__Now write some basic HTML inside dist/index.html__ <br/>

```html
<body>
  <h1>Hello world</h1>
  <script src="/main-bundle.js"></script>
</body>
```

__continue editing config/webpack.js__ <br/>

```javascript
const path = require("path")

module.exports = {
  entry:{
    main: "./src/main.js"
  },
  mode: "development",
  output: {
    filename: "[name]-bundle.js",
    path: path.resolve(__dirname, "../dist"),
    publicPath: "/"
  },
  devServer: {
    contentBase: "dist"
  }
}
```

__install webpack for server locally__ <br/>

```terminal
npm install -S webpack webpack-cli webpack-dev-server
```

And exec: <br/>

```terminal
webpack-dev-server --config=config/webpack.dev.js
```














