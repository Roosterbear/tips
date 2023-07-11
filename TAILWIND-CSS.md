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