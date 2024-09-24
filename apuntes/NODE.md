# NODE.js

### Playing with NODE

* In a terminal, create a new folder to your project.
* Then create the init file inside the folder of your project: 

```terminal
npm init
```

* We can play with packages in the site: __npmjs.com__
* To install a new package, we can type: 

```terminal
npm i sillyName
```

* And we can use it in our index.js like:

```javascript
var generateName = require("sillyName");
var sillyName = generateName();
console.log(`My name is: ${sillyName}`);
```

### Change to module

* We need to edit our package.json and add below "main":

```json
"type": "module",
```

* Then we change our index.js:

```javascript
import generateName from "sillyName";
```

### Create a Server with EXPRESS

* In a terminal, create a new folder to your project. Ex. _mkdir express-server_ 
* Now create a file inside it: 

```bash
touch server.js
```

* Then create the init file inside the folder of your project: 

```bash
npm init
```

### Install express

```bash
npm install express --save
```






