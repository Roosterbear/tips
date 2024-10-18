# NPM

## INIT

* Create package.json
>npm init

* Create package.json without filling information
>npm init -y


## PACKAGE.JSON

* In the second section, we can add our "dependencies"
* Also we can add our dependencies for develompent ambient as "devDependencies"

```json
"dependencies":{
  "bootstrap":"^4.3.1",
  "cors":"^2.8.5",
  "express":"^4.17.1"
},
"devDependencies":{}
```

__list dependencies__ <br/>

```bash
npm list
```

__list dependencies in a simple way (main level)__ <br/>

```bash
npm list --depth 0
```

__list global dependencies__ <br/>

```bash
npm list --g
```

__adding or deleting dependencies__ <br/>

* Add or delete dependencies in the JSON file and then:

```bash
npm install
```


### START

* To load an application, we can add a "start" item in the first section:

```json
{
  "name":"my_project",
  "version":"1.0",
  "description":"My project",
  "main":"index.js",
  "scripts":{
    "start": "node app.js"
  }
}
```

### SEARCH PACKAGES

* Looking for a package about animations:

>npm search animations



__problems with permissions in NPX__ _create-react-app_ <br/>

```terminal
npm config get prefix
```

__check our installation state:__ <br/>

```terminal
npm doctor
```
If there is a problem, any issue will be indicated in red color. <br/>


__solve the permissions problem with npm__ <br/>

>create a folder in the user home:

```terminal
mkdir ~/.npm-global
```

>set as NPM prefix

```terminal
npm config set prefix '~/.npm-global'
```

>adding path in our ~/.bashrc or ~/.zshrc

```terminal
export PATH=~/.npm-global/bin:$PATH
```

>restart terminal and check the state again: 

```terminal
npm doctor
```




