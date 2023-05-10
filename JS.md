# Javascript

### Button to add elements at the end of a list
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.append(li);
});
```
### Button to add elements at the end of a list
```javascript
const button = document.querySelector('button');

button.addEventListener('click', ()=>{
  const li = document.createElement('li');
  li.textContent = 'Something to do';
  ul.prepend(li);
});
```
### Delete elements of a list added lately
```javascript
ul.addEventListener('click', e=>{
  if(e.target.tagName === 'LI'){
    e.target.remove();
  }
});
```

### Button to delete an element from the list
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.remove();
  });
});
```
### Button to strikethrough an element from the list
```javascript
const items = document.querySelectorAll('li');

items.forEach.(item=>{
  item.addEventListener('click', e=>{
    e.target.style.textDecoration = 'line-through';
  });
});
```
---
## CREATE A POP-UP
### HTML
```html
<button>click me!</button>
<div class="popup-wrapper">
  <div class="popup">
    <div class="popup-close">x</div>
    <div class="popup-content">
      <h2>HOT SALE!</h2>
      <p>50% off Hot panties and tights !</p>
      <a href="#">View</a>
    </div>
  </div>
</div>
```
### CSS
```css
button{
  display: block;
  margin: 20px auto;
  background: crimson;
  color: white;
  border: 0;
  padding: 6px 10px;  
  // Ocultar popup al inicio
  display: none;
}

.popup-wrapper{
  background: rgba(0,0,0,0.5);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.popup{
  font-family: arial;
  text-align: center;
  width:100%;
  max-width: 300px;
  margin: 10% auto;
  padding: 20px;
  background: white;
  position: relative;
}

.popup a{
  background: crimson;
  color: white;
  text-decoration: none;
  padding: 6px 10px;
}

.popup-close{
  position: absolute;
  top: 5px;
  right: 8px;
  cursor: pointer;
}
```
### Javascript
```javascript
const  button = document.querySelector('button');
const  popup = document.querySelector('popup-wrapper');
const  close = document.querySelector('popup-wclose');

button.addEventListener('click', ()=>{
  popup.style.display = 'block';
});

close.addEventListener('click', ()=>{
  popup.style.display = 'none';
});

popup.addEventListener('click', ()=>{
  popup.style.display = 'none';
});
```

