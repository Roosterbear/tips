# Javascript

## Botón para agregar elementos al <u> final </u> de la lista
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.append(li);
});
```
## Botón para agregar elementos al inicio de la lista
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.prepend(li);
});
```
## Para eliminar elementos de lista agregados recientemente
```javascript
ul.addEventListener('click', e=>{
  if(e.target.tagName === 'LI'){
    e.target.remove();
  }
});
```

## Botón para eliminar un elemento de lista
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.remove();
  });
});
```
## Botón para tachar texto de un elemento de lista
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.style.textDecoration = 'line-through';
  });
});
```



