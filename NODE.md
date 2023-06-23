# NODE.js

### Playing with NODE

In a terminal, create a new folder to your project. <br/>

Then create the init file inside the folder of your project: <br/>

```terminal
npm init
```

We can play with packages in __npmjs.com__: <br/>
To install a new package, we can type: <br/>

```terminal
npm i sillyName
```

And we can use it in our index.js like: <br/>

```javascript
var generateName = require("sillyName");
var sillyName = generateName();
console.log(`My name is: ${sillyName}`);
```

### Change to module

We need to edit our package.json and add below "main": <br/>

```json
"type": "module",
```

Then we change our index.js: <br/>

```javascript
import generateName from "sillyName";
```

### Create a server withe EXPRESS

In a terminal, create a new folder to your project. Ex. _mkdir express-server_ <br/>
Now create a file inside it: <br/>

```terminal
touch server.js
```

Then create the init file inside the folder of your project: <br/>

```terminal
npm init
```

__install express__ <br/>

```terminal
npm install express --save
```






