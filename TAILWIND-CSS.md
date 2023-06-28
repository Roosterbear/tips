# Tailwind CSS

__start__ <br/>

The best way to start is creating a folder of our project, entering on it and run: <br/>

```terminal
npm init -y
```

Now is time to install all we need: <br/>

```terminal
npm i tailwindcss postcss-cli autoprefixer @tailwindcss/jit
```

Create the folders: __src__, __public__, __public/css__ <br/>
Then create a file: _public/css/index.html_ <br/>
And a file: _./tailwind.config.js_ and _./postcss.config.js_ <br/>

Now config __postcss.config.js__: <br/>

```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
}
```

And __tailwind.config.js__: <br/>

```javascript
module.exports = {
  purge: [
    '.public/**/*.html',
  ],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {}
  },
  variants: {
    extend: {},
  },
  plugin: [],
}
```

Now create a file tailwind.css inside __src__ folder. And add the next directives: <br/>

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Install extension: __Tailwind CSS Intellisense__ <br/>
Edit settings: (ctrl+p) <br/>
Uncheck in _css.validate_ <br/>
Edit in _editor.quicksuggestions_ and add an object with: <br/>

```javascript
"editor.quickSuggestions":{
  "strings": true
}
```

Open package.json and edit: <br/>

```json
"scripts":{
  "build:css":"postcss ./src/tailwind.css -o ./public/css/main.css",
  "build":"NODE_ENV=production postcss ./src/tailwind.css -o ./public/css/main.css"
}
```

_in windows, add the package:_ <br/>

```terminal
npm i win-node-env
```

Now run: <br/>

```terminal
npm run build:css
```

The comand above adds all we need to use __tailwind__ <br/>

And just add the link: <br/>

```html
<link rel="stylesheet" href="css/main.css">
```

When we finish our site, we can run: <br/>

```terminal
npm run build
```

And our __main.css__ will have just the essential classes to our customized site, and will _remove_ all we didn't use. <br/>


