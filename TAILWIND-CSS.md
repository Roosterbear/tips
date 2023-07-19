# Tailwind CSS

__start__ <br/>

Create a folder for your project. <br/>

Open that folder in Visual Studio Code. <br/>

Check that you have NodeJS updated, open terminal in that folder and write: <br/>

```terminal
npm init -y
npm install -D tailwindcss postcss postcss-cli autoprefixer
npx tailwindcss init
```
Create _postcss.config.js_ in the root and copy the code: <br/>

```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

Edit __tailwind.config.js__: <br/>

```javascript
module.exports = {
  content: ["./public/**/*.html"],
    theme: {
      extend: {},
    },
  plugins: [],
}
```

Create a _Tailwind_ folder, and the __main.css__ file inside and add: <br/>

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Open package.json file and edit in script: <br/>

```json
"build": "tailwind build -i Tailwind/main.css -o public/tailwind.css"
```

Now run in terminal: <br/>

```terminal
npm run build
```

Link the _tailwind.css_ created in a __index.html__ file inside the __public__ folder. <br/>

Add the class _text-red_ to a paragraph to test. <br/>

__Look that we can not see the changes, we have to rebuild.__ <br/>

To avoid this, we can add a __watch__ mode in our _package.json_: <br/>

```json
"scripts": {
    "build": "tailwind build -i Tailwind/main.css -o public/tailwind.css",
    "watch": "tailwind build -i Tailwind/main.css -o public/tailwind.css -w"
  },
```

Now run: <br/>

```terminal
npm run watch
```

__optimize for production__ <br/>

Edit _package.json_ to use __POSTCSS__: <br/>

```json
"scripts": {
    "build": "postcss Tailwind/main.css -o public/tailwind.css",
    "watch": "postcss Tailwind/main.css -o public/tailwind.css -w"
  },
```
_now run watch again_ <br/>

## POSTCSS

__Plugin__          Description <br/>
<br/>
__autoprefixer__ 	      Añade prefijos CSS automáticamente, basándose en CanIUse. <br/>
__css-modules__ 	      Aplica la estrategia CSS Modules para aislar CSS y evitar la cascada. <br/>
__stylelint__ 	        Linter de código CSS, compatible también con preprocesadores como LESS o Sass. <br/>
__postcss-preset-env__ 	Convierte CSS no soportado por navegadores en CSS soportado. El Babel de CSS. <br/>
__cssnano__ 	          Minificador de código CSS. <br/>
__purgecss__ 	          Elimina código CSS muerto (no utilizado) de nuestros proyectos. <br/>
<br/>






