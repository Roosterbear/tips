# GIT HELP 
## The most used commands

> FIRST PROJECT 

#### Create a repository

```git
git init
```

#### Add to staged area [All files]

```git
git add .
```

#### Commit changes [with a message]

```git
git commit -m "First commit"
```

#### Now create a GitHub proyect

#### Get a project ####

```git
git remote add origin https://github.com/Roosterbear/your-proyect.git
git branch -M main
```

#### You can use Visual Studio Code to push easily 
or...
```git
git push -u origin main
```

## List commits

```
git log
```

## 

#
> MOVING ON GIT

#### What branch we are

```git
git branch
```

#### Change branch

```git
git checkout coworker
```

#### Deleting a branch

```git
git branch -d coworker
```

#### View the log of commits

```git
git log --pretty=oneline
```

## Initial Configurations
> INITIAL (Just the first time configuration)

#### Basic configuration
```git
git config --global user.name "Roosterbear"

git config --global user.email "fernandoroosterbear@gmail.com"
```

## ERRORS
__fatal: rehusando fusionar historias no relacionadas__ <br/>
git pull --allow-unrelated-histories origin main

__Backwards commit__ <br/>

```git
git commit --amend
```

__Delete a file in repository without deleting the local__ <br/>

```git
git rm --cached file.txt
```
__Delete a whole directory in repository without deleting the local__ <br/>

```git
git rm --cached -r directory
```
