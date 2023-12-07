# GRID Layout

The best way to create complex designs with different size blocks in 2 DIMENSION ALIGMENT. <br/>
in some ways, it moves like _tetris_ <br/>

__1.- We need a parent class to contain Grid Layout:__ <br/>
```css
.grid-layout{
  display: grid;  
}
```

__2.- We have to say how many rows and columns I want:__ <br/>
```css
.grid-layout{
  display: grid; 
  grid-template-columns: auto 1fr;
  grid-template-rows: 100px 50%;
}
```
_This way, every auto or value are a column._<br/>

__3.- Size of an element:__ <br/>
```css
.box1{
  grid-column: 1/3;
}
```
Where 1 is the first line (not the space ❗). <br/>

```css
.box2{
  grid-row: span: 2;
}
```

__4.- Position of the element:__ <br/>

```css
.astronaut{
  background-color: #03989e;
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 3;
}
```

Also we can use just grid-area to set the 4 values: <br/>
```css
.cowboy{
  grid-area: 2 / 1 / 3 / 3; 
}
```
Where the order is: <br/>
1.- grid-row-start <br/>
2.- grid-column-start <br/>
3.- grid-row-end and <br/>
4.- grid-column-end <br/>
