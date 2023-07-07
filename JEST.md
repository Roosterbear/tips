# Testing in Javascript with JEST

__Install Jest__ <br/>

_create a tests folder inside project_ <br/>

```terminal
npm init
```

_npm install --save-dev jest_ <br/>

_configure_ <br/>

```terminal
npx jest --init
```

Then _add json, no typescript, node, reports, v8, clean mocks_ <br/>

_copy the file to test_ <br/>

Just let the function to test, and below, add: <br/>

```javascript
module.exports = myFunction;
```

Where "myFunction" is actually the name of our function. <br/>

_create the test file_ like: "myfile.test.js" and add:<br/>

__test if function exists__ <br/>

```javascript
const myfunction = require("./myfile.js");

test("Test if the function is defined", ()=>{
  expect(myFunction).toBeDefined();
});
```

__test function__ <br/>

```javascript
const myfunction = require("./myfile.js");

test("Test if the function is defined", ()=>{
  expect(myFunction).toBeDefined();
});

test("It's a palindrome", ()=>{
  expect(myFunction("otto")).toEqual(true);
});

test("It isn't a palindrome", ()=>{
  expect(myFunction("leonard")).toEqual(false);
});

```






