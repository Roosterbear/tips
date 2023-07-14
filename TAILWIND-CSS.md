# Tailwind CSS

__start__ <br/>

Create a folder for your project. <br/>

Open that folder in a terminal and install: <br/>

```terminal
npx install -D tailwindcss postcss autoprefixer
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
Now run in terminal: <br/>

```terminal
npm init -y
```

Open package.json file and edit in script: <br/>

```json
tailwind build -i Tailwind/main.css -o public/tailwind.css
```

Now run in terminal: <br/>

```terminal
npm run build
```

Link the tailwind.css in the __HTML__ file. Add the class _text-red_ to a paragraph to test. <br/>

Look that we can not see the changes, we have to rebuild. <br/>

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

Edit _package.json_ to use __postcss__: <br/>

```json
"scripts": {
    "build": "postcss Tailwind/main.css -o public/tailwind.css",
    "watch": "postcss Tailwind/main.css -o public/tailwind.css -w"
  },
```

_now run watch again_ <br/>








