# Vue.js Getting started with npm and webpack

- [vue.js](https://vuejs.org/)
- [vue.js (J)](https://jp.vuejs.org/)

## Requirement

- vue.js
- webpack
- vue-router
- babel
- jquey

## Usage
### Prerequirement Confirmation Command

- Node version
  - `node -v`
- NPM version
  - `npm -v`
- webpack version
  - `webpack -v`
  - If it does not exist:
    - `npm install -g webpack`
    - `-g` : GLOBAL Option

### Project Structure

```
├── LICENSE
├── README.md
├── app
│   ├── index.html
│   └── scripts
│       └── bundle.js
├── bs-config.json
├── package.json
├── src
│   ├── components
│   │   └── app.vue
│   └── scripts
│       └── index.js
└── webpack.config.js
```

### Package Installation

```
npm install
```

これで必要なパッケージがインストールされるはず。

#### package.json

```json
{
  "name": "npm-webpack-vuejs",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "webpack": "webpack -w",
    "lite": "lite-server",
    "start": "concurrently \"npm run lite\" \"npm run webpack\""
  },
  "keywords": [],
  "author": "shinyay",
  "license": "MIT",
  "dependencies": {
    "jquery": "^3.2.1",
    "vue": "^1.0.28",
    "vue-router": "^0.7.13"
  },
  "devDependencies": {
    "babel": "^6.23.0",
    "babel-core": "^6.24.1",
    "babel-loader": "^6.4.1",
    "babel-plugin-transform-runtime": "^6.23.0",
    "babel-preset-es2015": "^6.24.1",
    "concurrently": "^2.2.0",
    "css-loader": "^0.23.1",
    "lite-server": "^2.3.0",
    "vue-html-loader": "^1.2.4",
    "vue-loader": "^8.7.0",
    "vue-style-loader": "^1.0.0",
    "webpack": "^1.15.0"
  }
}
```
中身はこんな感じ。
けっこういろいろはいってますね。

#### Packages

##### Babel
```
npm install --save-dev babel
```

##### babel-core
Babel Compiler Core component

```
npm install --save-dev babel-core
```

[https://www.npmjs.com/package/babel-core](https://www.npmjs.com/package/babel-core)
[https://github.com/babel/babel/tree/master/packages/babel-core](https://github.com/babel/babel/tree/master/packages/babel-core)

##### babel-loader
Transpiling JavaScript files using Babel and webpack

```
npm install --save-dev babel-loader
```

[https://www.npmjs.com/package/babel-loader](https://www.npmjs.com/package/babel-loader)
[https://github.com/babel/babel-loader](https://github.com/babel/babel-loader)

##### babel-preset-es2015
Babel preset for all es2015 plugins

```
npm install --save-dev babel-preset-es2015
```


##### babel-plugin-transform-runtime
Externalise references to helpers and builtins, automatically polyfilling your code without polluting globals

```
npm install --save-dev babel-plugin-transform-runtime
```

##### vue-loader
Vue.js component loader for Webpack

```
npm install --save-dev vue-loader
```

##### concurrently
Run multiple commands concurrently
```
npm install --save-dev concurrently
```
[https://www.npmjs.com/package/concurrently](https://www.npmjs.com/package/concurrently)
[https://github.com/kimmobrunfeldt/concurrently](https://github.com/kimmobrunfeldt/concurrently)

##### lite-server
Lightweight development only node server that serves a web app, opens it in the browser, refreshes when html or javascript change, injects CSS changes using sockets, and has a fallback page when a route is not found

```
npm install --save-dev lite-server
```
[https://www.npmjs.com/package/lite-server](https://www.npmjs.com/package/lite-server)
[https://github.com/johnpapa/lite-server](https://github.com/johnpapa/lite-server)

##### webpack
webpack is a module bundler. Its main purpose is to bundle JavaScript files for usage in a browser, yet it is also capable of transforming, bundling, or packaging just about any resource or asset

```
npm install --save-dev webpack
```
[https://www.npmjs.com/package/webpack](https://www.npmjs.com/package/webpack)
[https://github.com/webpack/webpack](https://github.com/webpack/webpack)

##### vue
Vue.js

```bash
npm install --save vue
```
[https://www.npmjs.com/package/vue](https://www.npmjs.com/package/vue)

For loading vue.js not with script tag but with require

##### vue-router
vue-router is the official router for Vue.js. It deeply integrates with Vue.js core to make building Single Page Applications with Vue.js

```
npm install --save vue-router
```
[https://www.npmjs.com/package/vue-router](https://www.npmjs.com/package/vue-router)

For loading vue.js not with script tag but with require

##### jquery
jQuery

```
npm install --save jquery
```
[https://www.npmjs.com/package/jquery](https://www.npmjs.com/package/jquery)

For using it with webpack.ProvidePlugin

##### css-loader
```
npm install --save-dev css-loader
```
For css in vue file

##### vue-style-loader
```
npm install --save-dev vue-style-loader
```

For css in vue file

##### vue-html-loader
```
npm install --save-dev vue-html-loader
```

For html in vue file

### Scripts in package.json
Run multiple command with using concurrently:

```json
"scripts": {
  "webpack": "webpack -w",
  "lite": "lite-server",
  "start": "concurrently \"npm run lite\" \"npm run webpack\""
},
```

`npm start` make the folling commands run:

- `npm run lite`
- `npm run webpack`
  - `webpack -w`: monitoring



### bs-config.json
Configuration for light-server
```json
{
  "injectChanges": "true",
  "files": ["./app/**/*.{html,htm,css,js}"],
  "watchOptions": { "ignored": "node_modules" },
  "server": { "baseDir": "./app" }
}
```
