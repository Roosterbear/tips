# Tailwind CSS

__start__ <br/>

```terminal
npx tailwindcss init
```

It will create _tailwind.config.js_ <br/>

__Create folders:__ _build_ with index.html file, and _src_ <br/>

__Config tailwind__ <zbr/>

In tailwind.config.js edit content bracket: <br/>

```javascript
content:['./build/*.html'],
```

Inside _src_ folder, ad the __input.css__ file and add: <br/>

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

* In VSC we have to change preferences - configuration - Unknown At Rules CSS Lint to __ignore__ <br/>

__Config files__ <zbr/>

In terminal, run: <br/>

```terminal
npx tailwinds -i ./src/input.css -o ./build/css/style.css
```

