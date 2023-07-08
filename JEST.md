# Testing in Javascript with JEST

__Install Jest__ <br/>

_create a jest-test folder_ <br/>

```terminal
npm init -y
```

_npm install --save-dev jest_ <br/>
or <br/>
_npm i -D jest_ <br/>

_edit package.json and add_ __jest__ _inside test_ <br/>

__Create the project__ <br/>

Create __src__ folder and __calculator__ folder inside. <br/>
Add __index.js__ file inside and write: <br/>

```javascript
module.exports = {
  sum(a, b){
    return a+b;
  }
}
```
Add __calculator.test.js__ file inside and write: <br/>

__FIRST TEST__ <br/>

```javascript
test('Empty test, it will pass', ()=>{
  //
});

test.todo('I will do this, some day...');
```
## RUN

```terminal
npm jest
```

  __SECOND TEST__ <br/>

```javascript
const calculator = require('.');

test('Testing function to add two numbers...', ()=>{
  const result = calculator.sum(1,2);
  expect(result).toBe(3);
});

test.todo('I will do this, some day...');
```

## MATCHERS




