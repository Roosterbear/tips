# REACT

## React commands and code

__create react app with CRA__

```node
npx create-react-app my-project
```

It will create the folder for you... or:<br/>

```node
mkdir my-project
cd my-project
npx create-react-app ./
```

__create react app with VITE__

```node
yarn create vite
```

We will be asked for the app name. _Give a name._<br/>
We will be asked for type, we type: React <br/>
We will be asked for language, type: Javascript <br/>

```node
yarn
yarn dev
```

---

__brand new and clean project__ <br/>

Delete the the _src_ folder <br/>
__We can only let the index.js and App.js to start working if you want 🍜__ <br/>
__index.js starts App.js, and we can just start with:__ <br/>

```react
const App = ()=> {
  return (
    <div>Hello</div>
  );
}

export default App;
```

or, deleting everything... <br/>
Now, make a new file named _main.jsx_ <br/>
Include: <br/>

```react
import React from 'react';
import ReactDOM from 'react-dom/client';

// We have to import a file we will use:
import HelloWorld from './HelloWorld';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App/>
  </React.StrictMode>
);
```

In the lines above, we imported the HelloWorld component, now we are going to create it. _(HelloWorld.jsx)_ <br/>

```react
export const HelloWorld = ()=>{
  return(
    <h1>Hello World</h1>
  )
}
```
__adding bootstrap__ <br/>

Edit the index.html in the __public__ _folder_, and in the header add the Twitter Bootstrap CDN:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

__adding proptypes in yarn__ <br/>

First, in command line type:

```node
yarn add prop-types
```

Now we can use it... <br/>

```react
import PropTypes from 'prop-types';

export const FirstApp = ({title, subtitle})=>{
  return(
    <>
      <h1>{title}</h1>
    </>
  )
}
```


__inline style - whith the style property__ <br/>

Usually, we just add style in HTML with their properties, <br/>
but in a component, we have to add it with javascript. <br/>
So, we have to put curly braces once to _add_ JS code, <br/>
and twice because is CSS. <br/>

```react
<h1 style={{color: #FF8C00}}>Hello world</h1>
```

__property CSS names in react__ <br/>

In CSS, we use a dash to separate words of the property name. <br/>
In React, we use Javascript, so we can not use dash for our names. <br/>
Instead of that we can use _camelCase_, Example: "__backgroundColor__" <br/>

```react
<h1 style={{color: #FF8C00, backgroundColor: #FF2D00}}>Hello world</h1>
```

To understand why we have 2 curly braces by side, we can use a variable to keep our CSS data:

```react
const styles = {
  color: #FF8C00;
  backgroundColor: #FF2D00;
}

return(
  <h1 style={styles}>Hello world</h1>
)
```

### Typical component

We can use a normal function, but is more commonly to find arrow functions: <br/>

```jsx
const myComponent = ()=>{
  return <h1>myComponent</h1>
}

export default myComponent;
```
If we return only one line, we can even skip the return. <br/>
If we return multiple lines of code, we can use parenthesis. <br/>

```jsx
const myComponent = ()=>{
  return (
    <>
      <div>myComponent</div>
      <h1>This is a test</h1>
    </>
    )
}

export default myComponent;
```

### Inject HTML code

```jsx
class App extends Component{
  state = {
    marcado: `
    <h1>Injecting HTML code...</h1>
    <br/>
    <hr/>
    <a href='#'>Link</a>
    `
  }  
  render(){
     return(
      <div
      dangerouslySetInnerHTML={{__html: this.state.marcado}}>
      </div>
    ) 
  }
}
```

### Build and deploy a project 👾 

First, we have to check the line "scripts" in package.json, and be sure that the build is set. Then:

```terminal
npm run build
npm install --global surge
surge
```

We will be asked to write our email  and password to create an account. <br/>
Now we have to write the path, we need to add "build", only to upload that folder. <br/>
We get a fake domain to use our project. <br/>
<br/>
__changes__ <br/>
We have to build again... and  update __surge__ with:<br/>

```terminal
surge --domain our-fake.domain.sh
```

Remember to add "build" to the path, and you're done! <br/>





---

<br/>

---



---

<br/>

---

# Next

Next.js is a __Framework__ to build web applications. Provides additional structure, features and optimizations. <br/>

```node
npx create-next-app my-next-app
cd my-next-app
npm run dev
```

Now we can create a new page: hello.js <br/>

```react
export default function Hello(){
  return(<h1>Hello NextJS</h1>)
}
```
Now we can see it in: _localhost:3000/hello_ <br/>

__creating links to navigate__

```react
<Link href="/directory/file">
  <h1>Click here</h1>
</Link>
```

__creating dynamic routes__

Create a file like [name].js <br/>

```react
import {useRouter} from "next/router"
import topics from "../api/topics" // Array with the data

export default function Learn(){
  const router = useRouter()
  const {name} = router.query
  const topic = topic.find(topic => topic,id === name)
  
  return(<h1>Learn {topic.id}</h1>)
}
```

The topics.js

```javascript
export default{
  id: 'angular',
  about:'Is a development platform in Typescript'
},
{
  id:'vue',
  about:'Is a progressive framework'
}
```

```react
<Link href="/learn/angular">
  <h2>Learn Angular</h2>
</Link>
```











