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


```css
html{
  text: none;
}
```


```javascript
```

