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

Now create a file tailwind.css inside __src__ folder. <br/>
