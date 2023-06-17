# NODE.js

In a terminal, create the init file inside the folder of your project:

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

### change to module

We need to edit our package.json and add below "main": <br/>

```json
"type": "module",
```

Then we change our index.js: <br/>

```javascript
import generateName from "sillyName";
```

