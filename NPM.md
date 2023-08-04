# NPM

## All about NPM

__problems with permissions in NPX__ _create-react-app_ <br/>

```terminal
npm config get prefix
```

> /usr

The executables of command line will be installed at __/usr/bin__ <br/>
And the packets in __/usr/lib/node_modules__ and so on. <br/>

__check our installation state:__ <br/>

```terminal
npm doctor
```

If there is a problem, any issue will be indicated in red color. <br/>

__solve the permissions problem with npm__ <br/>

### create a folder in the user home:

```terminal
mkdir ~/.npm-global
```

### set as NPM prefix

```terminal
npm config set prefix '~/.npm-global'
```

### adding path in our ~/.bashrc or ~/.zshrc

```terminal
export PATH=~/.npm-global/bin:$PATH
```

restart terminal and check the state again: <br/>

```terminal
npm doctor
```




