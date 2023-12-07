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

## Lines

* By default, a line has no color
* To change color, use _stroke_
>stroke="red"
* To change width, use _stroke-width_
>stroke-width="10"



















