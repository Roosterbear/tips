# MongoDB

### Instal on Linux && Mac 

1. Download the TAR file of MongoDB
2. Extract the folder and delete the source file.
3. Open a terminal and type: _sudo mv_ and drag the folder to terminal to copy the path.
4. Now write the destiny path: _usr/local/mongodb_ 
5. Go to Home directory and create a bash file, then edit it:

```bash
cd ~
touch .bash_profile
vim .bash_profile
```

6. Add the line: _export PATH=$PATH:/usr/local/mongo/bin_ and save the file.

7. Create the folder:

```terminal
mkdir -p /data/db
```

8. Now change permissions:

```terminal
sudo chown lf /data/db
```
9. __CLOSE__ terminal

10. check version with: _mongo --version_


### Install on Windows

1. Download installer
2. Next - Accept - Complete
3. Select: Run service as Network service user
4. Copy installation path
5. Uncheck install compass - Next - Install -- Finish
6. Enter the path of installation, then _bin_ folder 
7. Create de folder: _C:\data/db 
8. Use a linux terminal terminal (cmder, gitbash)
9. Create a file with: touch .bash_profile
10. Edit it with _vi_ and add:

```BASH
alias mongodb="/c/Program\ files/MongoDB/Server/4.3/bin/mongod.exe"
alias mongo="/c/Program\ files/MongoDB/Server/4.3/bin/mongo.exe"
```

11. __CLOSE__ terminal

12. Check version with: _mongo --version_



## RUN MONGO ENGINE

In Terminal Type: _mongod_ 

> If launchs an SocketException Error: Address already in use, check old instance:

```bash
sudo lsof -iTCP -sTCP:LISTEN -n -P
```
> Then kill process:

```bash
sudo kill ###
```
> Where _###_ is the PID. 



# RUN MONGO TERMINAL

* In Terminal Type: _mongo_ (without "d") <br/>

* We will end with a prompt like: __>__ <br/>

* We can use _help_ 



## Managing DBs

* SHOW DBs: 

```shell
show dbs
```

* Using a clean DB:

```shell
use shopDB
```

* Now we are switched to db __shopDB__ 

* The __shopDB__ was created, but it needs to have information to be shown with __show dbs__ 

* Know current DB:

```shell
db
```


## Managing Collections (TABLES)

* Create the _products_ __collection__: 

```shell
db.products.insertOne({_id:1, name:"Pen", price:1.20})
```

* Show Collections

```shell
show collections
```


## Queries

* Search for id 1

```sql
db.products.find({_id:1})
```

* Search for all IDs greater than 1

```sql
db.products.find({_id:{$gt:1}})
```

__$gt__   greater than
__$gte__  greater or equal than
__$lt__   less than
__$lte__  less or equal than
__$ne__   not equal than
__$in__   any value in the array
__$nin__  none of the values in array




