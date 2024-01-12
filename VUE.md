# VUE

- Small, Easy, reusable and Simple to integrate

## VUE in a simple way ---SHOWING A MESSAGE---

```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<div id="app">
  <p>{{title}}</p>
</div>
<script src="app.js"></script>
```

```javascript
new Vue({
  el:'#app',
  data:{
    title:'Hellow World!'
  }
});
```

## VUE in a simple way ---USING A METHOD---

```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<div id="app">
  <p>{{title}}</p>
  <button v-on:click='changeTitle'>Change Title</button>
</div>
<script src="app.js"></script>
```
- We can change _v-on:click_ by __@click__

```javascript
new Vue({
  el:'#app',
  data:{
    title:'Hello World'
  },
  methods:{
    changeTitle(){
      this.title='Change Title';
    }
  }
});
```

## VUE in a simple way ---ADDING STYLE---


```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<div id="app">
  <input type="text" v-on:input="cssClass=$event.target.value">
  <p v-bind:class="cssClass">Class: {{cssClass}}</p>
</div>
<script src="app.js"></script>
```
- We can change _v-bind:class_ by just __:class__

```javascript
new Vue({
  el:'#app',
  data:{
    cssClass:''
  }
});

```

```css
.red{
  background-color:red;
}

.blue{
  background-color:blue;
}
```



