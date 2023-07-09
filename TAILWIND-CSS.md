# Tailwind CSS

__start__ <br/>

We will need Node.js <br/>

There are 3 ways to install Tailwind: <br/>

1.- Using CDN Link <br/>
2.- Using Tailwind CLI <br/>
3.- Using PostCSS <br/>

__using CDN__ <br/>

Go to Tailwind page and copy the link and paste it in the header: <br/>

```html
<script src="https://cdn.tailwindcss.com"></script>
```
__using CDN__ <br/>

_check documentation in official page_ <br/>

<br/>

__using PostCSS__ <br/>

In our project folder: <br/>

```terminal
npm install -D tailwindcss postcss autoprefixer
```


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
Edit settings: (ctrl+p and type: settings) or ctrl+,<br/>
Uncheck in _css.validate_ <br/>
Edit in _editor.quicksuggestions_ to __on__ or add an object with: <br/>

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
---

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


---

__breakpoints__ <br/>

_xl:bg-red-500_ Cuando sea la pantalla XL, poner fondo red-500
_md:bg-blue-500_ Cuando sea la pantalla MD, poner fondo blue-500
_lg:justify-start_ Cuando sea la pantalla LG, poner elementos al principio
_sm:hidden_ Cuando sea la pantalla SM, esconder elementos
_bg-yellow-300_ En los demas casos, usar color yelloe-300

__components__ <br/>

It is like have classes. We can create a set of styles to some element. In our tailwind.css add: <br/>

.link{
  @apply #text-white block p-5 font-bold hover:text-yellow-500
}

__buttons__ <br/>

```html
<a href="#" class="border-4 border-yellow-400 text-white font-bold p-2 rounded-full">
<a href="#" class="rounded-full bg-red-500 text-white font-bold px-4 py-3 hover:text-black hover:bg-white transition duration-500">
```


__burguer menu__ <br/>

```html
<div class="block lg:hidden w-1/6 lg:w-4/6">
  <a href="#" class="link" id="mobile-menu">Menu</a>
  <ul class="mobile-links hidden w-full absolute z-50 left-0">
    <li><a href="#" class="link">Home</a></li>
</div>  

<script>
  const menuButton = document.querySelector('#mobile-menu');

  menuButton.addEventListener('click', e=>{
    const menu = document.querySelector('.mobile-links');
    menu.classList.toggle('hidden');
  });
</script>
```

