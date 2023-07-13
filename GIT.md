# GIT

🔥 __If we have a project in our local machine__ <br/>

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


🔥 __If we have a project in Github and we want it in our local machine__ <br/>

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


__View changes__ <br/>

```git
git status
```

🔥 __Merge branches__ <br/>

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

__empty folders__ <br/>

🔥🔥🔥 git does not upload empty folders !! 🔥🔥🔥 <br/>
<br/>


## GIT IGNORE 🔥🔥🔥

Create a file named _.gitignore_ <br/>

Add folders to be ignored kinda: folder1/ <br/>
Add files to be ignored just by: important.php/ <br/>

__see ignored__ <br/>

```git
git status --ignored
```

__exceptions in .gitignore file__ <br/>

```git
*.txt
!important.txt
```
_include file.txt besides txt files are ignored_ <br/>


__if a file is in an ignored folder__ <br/>

```git
!folder/
folder/*
!folder/*.txt
```

__Clear already commited files, but included in__ _.gitignored_ <br/>

```git
git rm -r --cached .
git add .
git commit -m "removing files included in .gitignore
git push origin main
```

## LOGS

__List commits__ <br/>

```git
git log
```
__QUIT__ with _q_ or _ctr+z_ <br/>

__Pretty List of commits__ <br/>

```git
git log --pretty=oneline
```

__Pretty List + graph commits__ <br/>

```git
git log --pretty=oneline --graph
```

__Just messages__ <br/>

```git
git shortlog
```

__Number of commits to show__ <br/>

```git
git log -10 --oneline
```

Will show 10 lines of commits <br/>

__Complete log__ <br/>

```git
git log --stat
```

__Complete info from a single commit__

```git
git show 1d6a825
```

## BRANCHES

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

__Create a new branch__ <br/>

```git
git checkout -b [branch_name]
```

__Change to a branch__ <br/>

```git
git checkout <branch_name>
```

__Change to a commit__ <br/>

```git
git checkout 1d6a825
```

__Rollback the LAST commit__ <br/>

```git
git reset --soft HEAD~
```

__Rollback a commit__ <br/>

```git
git reset --soft 1d6a825
```

__Discard PERMANENTLY any change in LAST commit__ <br/>

```git
git reset --hard HEAD~
```

__Discard PERMANENTLY any change in a commit__ <br/>

```git
git reset --hard 1d6a825
```


<br/><br/><br/><br/><br/>

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
