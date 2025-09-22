## Instalaciones

- [x] Visual Studio Code <br/>

__Ligaduras__ <br/>

* Instalar fuente JetBrains Mono
* File - Preferences - Settings
* Buscar "Ligatures" y edit in _settings.json_
* "editor.fontLigatures": true,

__Plugins__

* Markdown All in One (__ctrl+shift+v__ para preView)
* Tailwind CSS IntelliSense
<br/>

- [x] Vim <br/>

__Tabs de 2 espacios__ <br/>

* Ir a la carpeta del usuario
* Editar el archivo .vimrc (_si no existe, crearlo_)
* Agregar:

```bash
set expandtab
set shiftwidth=2
set tabstop=2
set softtabstop=2
```
<br/>

- [x] WSL (Linux en Windows) <br/>

```wsl --install -d Ubuntu```
__REINICIAR !!__
```sudo apt-get update```
```sudo apt install build-essential rustc libssl-dev libyaml-dev zlib1g-dev libgmp-dev```
<br/>

- [x] React <br/>

```npm create vite@latest proyecto -- --template react```
<br/>

- [x] TailwindCSS <br/>

1. Tener instalado Node, checar con ```node --version```
2. Crear carpeta de proyecto ```mkdir proyecto```
3. Entrar a carpeta ```cd proyecto```
4. Inicializar proyecto ```npm init```
5. Instalarle Tailwind ```npm add tailwindcss @tailwindcss/cli```
6. Crear archivos **tailwind.css** y **style.css**
7. Agregarle la linea ```@import "tailwindcss"``` al archivo de entrada
8. Agregar script al **package.json**: 
   ```"tw":"npx @tailwindcss/cli -i ./tailwind.css -o ./style.css --watch"```
9. Ejecutarlo con ```node --run tw```
10. Crear **index.html** y referenciar "_style.css_" 

- [x] Typescript <br/>

```npm install -g typescript```
```tsc -v```

* En Powershell
```Get-ExecutionPolicy -List```
```Set-ExecutionPolicy RemoteSigned -Scope LocalMachine```

- [x] Gulp <br/>

```npm install -g gulp-cli```
```gulp -v```

- [x] Ruby and Rails <br/>

```bash
curl https://mise.run | sh 
echo 'eval "$(~/.local/bin/mise activate)"' >> ~/.bashrc 
source ~/.bashrc
```

```mise use --global ruby@3```
```ruby --version```
```gem update --system```
```mise use --global node@22.13.0```
```node -v```
```gem install rails -v 8.0.1```
```rails -v```
```sudo apt install postgresql libpq-dev```
```sudo -u postgres createuser lf -s```

* Up postgresql

```sudo service postgresql start```

* Run Rails

```rails new proyecto -d postgresql```
```cd proyecto```
```rake db:create```
```rails server```

- [x] Vue <br/>

```npm init vite@latest proyecto -- --template vue```
```cd proyecto```
```npm install```
```npm run dev```

- [x] Angular <br/>

```npm install -g @angular/cli```
```ng -v```
```ng new proyecto```
```cd proyecto```
```ng serve --o```

- [x] Bootstrap in npm <br/>

```npm install bootstrap@5.3.3```

- [x] REDIS <br/>

```apt install redis-server redis-tools```


- [x] Visual Studio 2019 <br/>
  
> Buscar Visual Studio 2019 Community
> **Registrarse!** con una cuenta Microsoft
> Usar Framework 4


## Links

[Emoticons](https://emojikeyboard.top/es/) 😋<br/>
[Iconos](https://v2.boxicons.com/) <br/>
<br/>

---

- [x] Puerto Suizo
  
```baseg74441@angewy.com```
> 3~|"p527238K5[s"qm}8D8,.SgjDJL3N

[GUEA501128SX0]
> Alberto José Manuel Guerra Estevanez <br/>
> San Rafael N° 107, San Cayetano, Aguascalientes, Ags. 
**c.p. 20010**
```proyecta.guerra@gmail.com```
[NEGJ7503278N5]
> JUAN SERGIO NEVÁREZ GARCÍA
Scotiabank Cuenta: 25603789887 CLABE: 044010256037898878
cosetec@hotmail.com cosetecgerencia@hotmail.com
(449) 111-1403

