# Flexbox

__1.- We need a parent class to contain flexbox:__ <br/>

```css
.container{
  display: flex;
  gap: 1rem; 
}
```
>gap is the space between elements

* We need at least a child element.


__2.- We need to add the direction at that container with flex-direction:__ <br/>

```css
.container{
  display: flex;
  flex-direction: column; // Or by default: row
  gap: 1rem; // Space between elements
}
```
_We won't see anything until we add elements (items)_. <br/>

__Change the basis__ <br/>

The basis is the axis that we select in flex-direction. <br/>
We can change the size of every element with: <br/>

```css
.container > *{
  flex-basis: 100px;
}
```

__Wrap elements__ <br/>

By default, the elements are displayed in nowrap. <br/>
We must add to the parent: <br/>

```css
flex-wrap: wrap;
```

__Change order of elements__ <br/>

We can change the order of an element with: <br/>

```css
.first{
  order: 10; // will be displayed in the second place
}

.second{
  order: 0; // will be displayed in the first place
}
```

## justify-content

* flex-start 
* flex-end 
* center
* space-between 
* space-around
* space-evenly
<br/>

## align-items

❗ ONLY WORKS WITH NO-WRAP ❗ <br/>

* flex-start _Elements stick to the top edge_
* flex-end _Elements stick to the bottom edge_
* center _if elements have different height, they are centered by the middle in the center of the screen_
* baseline  _If elements have different height, they are centered by the middle in the top of the screen_
* stretch _Elements take all free space_

_To see how it works, we have to add to the parent:_

```css
height: 70vh;
```

_If we want to change the align of only one item we can use in that element:_

```css
align-self: flex-end; // or whatever we want...
```

## SIZING

```css
flex-grow: 0;
flex-shrink: 0;
```

## CENTER ELEMENTS

```css
display: flex;
justify-content: center;
align-items: center;
```

