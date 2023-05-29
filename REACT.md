# React

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
We will be asked for type. Type: React <br/>
We will be asked for language. Type: Javascript <br/>

```node
yarn
yarn dev
```

---



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
Instead of that we can: <br/>

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

---

<br/>

---

# React Native

React Native is a __Framework__ to build native movile apps, offering control and flexibility. <br/>
Expo CLI is a tool that simplify and accelerate the development of apps, giving an additional layer of abstraction. <br/>

__create a expo cli project__ <br/>

```node
npm install -g expo-cli
expo init AwesomeProject
cd AwesomeProject
npm start
```

__create a react native project__
```node
npx create-react-native-app uber-eats-clone
```

Choose _template_ <br/>
Choose _blank_ <br/>

```node
cd uber-eats-clone
```

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









