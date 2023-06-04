# GIT HELP 

__Create a repository localy in git__ <br/>

🔥 If we have a project in our local machine... <br/>

Go to the project folder and type: <br/>

```git
git init
git add .
git commit -m "First commit"
```

Now create a New project in __Github__ <br/>
In the __Code__ button, copy the link in __HTTP__. <br/>
Use this link in the code below. <br/>

```git
git remote add origin [https://github.com/Roosterbear/your-proyect.git]
git branch -M main
git push -u origin main
```
❗ Now the main branch is "main" and we have to change the name. <br/>


🔥 If we have a project in Github and we want it in our local machine... <br/>

```git
git clone https://github.com/Roosterbear/tips.git
```

Where _tips.git_ is the name of our project. <br/>
Now we have to change to the project directory. <br/>

```terminal
cd tips
```

It is better to create a new branch: <br/>

```git
git checkout -b local
```

Where _local_ is the name of our new local branch. <br/>

Now create our new local project: <br/>

```git
git add .
git commit -m "Message"
```

Now send your changes: <br/>

```git
git push origin local
```
‼️ REMEMBER TO SEND IT TO LOCAL BRANCH ‼️  <br/>

🔥 __Merge branchs__ <br/>

Go to the __main__ branch: <br/>

```git
git checkout main
```

Update the main branch: <br/>

```git
git pull origin main
```

Now just merge: <br/>

```git
git merge local
```

<br/>

__List commits__ <br/>

```git
git log
```

__Pretty List of commits__ <br/>

```git
git log --pretty=oneline
```

__What branch we are__ <br/>

```git
git branch
```

__Change branch__ <br/>

```git
git checkout [coworker]
```

__Deleting a branch__ <br/>

```git
git branch -d [coworker]
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
