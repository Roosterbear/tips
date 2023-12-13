# SVG

* SVG uses tags as __HTML__
* We can use SVG tags in HTML files
* To read __.svg__ files, we need to add the _STANDARD_ in XML as below

```html
<svg xmlsn="http://www.w3.org/2000/svg">
  <rect width="300" height="100" x="40" y="20" />
</svg>
```
* Extensions: __SVG__ by Jock, __SVG Preview__ by Simon Siefke and __SVG Snippets__ by Sidthesloth

## Rectangle

* We can make rectangles with the _rect_ tag
* By default, a shape is filled in __Black__
* To change color, use _fill_
* To change position, use _x_ and _y_

```html
<svg xmlsn="http://www.w3.org/2000/svg">
  <rect x="20" y="20" width="100" height="100" fill="blue">
</svg>
```

### Round Corners

* Use __rx__ to round corners
* The range is 1-50
>rx="5"
* You can either use __ry__
* If there is no _ry_, takes the same value as _rx_

## LINES

* By default, a line has no color
* To change color, use _stroke_
>stroke="red"
* To change width, use _stroke-width_
>stroke-width="10"

## CIRCLES

```html
<circle cx="200" cy="200" r="50"
fill="" fill-opacity="0.4"
stroke="rgb(0 0 0)" stroke-width="10" />
```


## ELLIPSE

```html
<ellipse cx="200" cy="400" rx="200" ry="50" fill="none" stroke="green" />
<ellipse cx="200" cy="00" rx="200" ry="50" fill="none" stroke="green" />
<ellipse cx="400" cy="200" rx="50" ry="200" fill="none" stroke="green" />
<ellipse cx="00" cy="200" rx="50" ry="200" fill="none" stroke="green" />


<ellipse cx="200" cy="200" rx="50" ry="200" fill="none" stroke="blue" 
transform="rotate(10 200 200)"/>
```
* In transform-rotate, the values are: (grades x y)
* We can increment by 10 grades to create an __atom__


## POLYLINE

```html
<polyline points="250 250 250 150 300 150 250 250"
fill="none" stroke="orange" transform="rotate(0 250 250)" />
```
* The shape can be closed or not
* We can increment by 30 grades to create a __flower__


## PATH

```html
<path d="M 20 20 L 200 20 V 50 H 20">
<path d="m 20 20 l 200 20 v 50 h 20">
<path d="M 90 20 C 5 45 165 65 60 100">
<path d="M 100 130 a 1 1 0 0 0 30 0">
<path d="M 130 100 a 2 2 0 0 0 0 30">
<path d="M 100 130 a 3 3 0 0 0 30 0">
<path d="M 100 100 a 4 4 0 0 0 0 30">
```
* Capital Letters consider coordinates absolute
* Small letters consider coordinates relatives to the previous point
* __M__ Move to
* __L__,__H__,__V__ Line to
* __C__,__S__ Cubic Bezier Curve
* __Q__,__T__ Quadratic Bezier Curve
* __Z__ Close path















