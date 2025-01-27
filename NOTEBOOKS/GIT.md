# GIT

- [GIT](#git)
  - [Configuración Inicial](#configuración-inicial)
  - [Subir un proyecto a Github](#subir-un-proyecto-a-github)
  - [Respaldar de forma LOCAL](#respaldar-de-forma-local)
  - [Ver cambios](#ver-cambios)
  - [LISTAR los commits](#listar-los-commits)
    - [Información completa de un commit](#información-completa-de-un-commit)
  - [BORRAR / Limpiar archivos subidos que queremos IGNORAR](#borrar--limpiar-archivos-subidos-que-queremos-ignorar)
  - [Actualizar una rama con otra](#actualizar-una-rama-con-otra)
  - [Eliminar una rama LOCALMENTE](#eliminar-una-rama-localmente)
  - [Eliminar una rama REMOTAMENTE](#eliminar-una-rama-remotamente)
  - [Checar ramas LOCALES y REMOTAS](#checar-ramas-locales-y-remotas)


## Configuración Inicial

```bash
git config --global user.name "Roosterbear"

git config --global user.email "fernandoroosterbear@gmail.com"
```

## Subir un proyecto a Github

1. Crear un nuevo Repositorio en Github
2. Agregar archivo - Subir archivos
3. Pestaña "Settings" - Pages - Branch "main"
4. Esperar unos minutos 🕜  

🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥🔥 <br/>

## Respaldar de forma LOCAL

1. Escribir desde la carpeta del proyecto en una consola:

```bash
git init
git add .
git commit -m "First commit"
```
2. Crear un proyecto nuevo en Github
3. Copiar link web del botón __code__ y usarlo en consola:

```bash
git remote add origin [https://github.com/Roosterbear/your-proyect.git]
git branch -M main
git push -u origin main
```

## Ver cambios

```bash
git status
```
## LISTAR los commits

```bash
git log --stat
git log
git log --pretty=oneline
git log --pretty=oneline --graph
```
> Salir con _q_

### Información completa de un commit

```bash
git show [xxxxx]
```
> [xxxx] Primeros caracteres del ID del commit

## BORRAR / Limpiar archivos subidos que queremos IGNORAR

```bash
git rm -r --cached .
git add .
git commit -m "removing files included in .gitignore
git push origin main
```

## Actualizar una rama con otra

1. Nos vamos a la rama a actualizar:

```bash
git checkout main
```
2. Checar la rama en la que estamos:

```bash
git branch
```

3. Bajar cambios DESDE la rama que tiene los cambios:

```bash
git merge pruebas
```

4. Publicar la actualización:

```bash
git add .
git commit -m "sincronizando desde pruebas"
git push
```

## Eliminar una rama LOCALMENTE

```bash
git branch -d pruebas
```

## Eliminar una rama REMOTAMENTE

```bash
git push origin --delete pruebas
```

## Checar ramas LOCALES y REMOTAS

```bash
git branch -a
```












