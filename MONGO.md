# MongoDB

### Linux && Mac 

1.- Download the TAR file of MongoDB <br/>
2.- Extract the folder and delete the source file. <br/>
3.- Open a terminal and type: _sudo mv_ and drag the folder to terminal to copy the path. <br/>
4.- Now write the destiny path: _usr/local/mongodb_ <br/>
Go to Home directory and create a bash file, then edit it:

```terminal
cd ~
touch .bash_profile
vim .bash_profile
```

Add the line: _export PATH=$PATH:/usr/local/mongo/bin_ and save the file. <br/>

Create the folder: <br/>

```terminal
mkdir -p /data/db
```

Now change permissions: <br/>

```terminal
sudo chown lf /data/db
```
__close terminal__ <br/>

check version with: _mongo --version_ <br/>

### Windows

Download installer <br/>
Next - Accept - Complete <br/>
Select: Run service as Network service user <br/>
Copy installation path <br/>
Uncheck install compass - Next - Install -- Finish<br/>
Enter the path of installation, then _bin_ folder <br/>
Create de folder: _C:\data/db <br/>
Use a linux terminal terminal (cmder, gitbash) <br/>
Create a file with: _touch .bash_profile_ <br/>
Edit it with _vi_ and add: <br/>

```terminal
alias mongodb="/c/Program\ files/MongoDB/Server/4.3/bin/mongod.exe"
alias mongo="/c/Program\ files/MongoDB/Server/4.3/bin/mongo.exe"
```

__close terminal__ <br/>

check version with: _mongo --version_ <br/>

## RUN MONGO ENGINE

In Terminal Type: _mongod_ <br/>


---

If launchs an SocketException Error: Address already in use, check old instance:

```terminal
sudo lsof -iTCP -sTCP:LISTEN -n -P
```
Then kill process:

```terminal
sudo kill ###
```

Where _###_ is the PID. <br/>

---

# RUN MONGO TERMINAL

__NOW RUN MONGO__ <br/>

In Terminal Type: _mongo_ (without "d") <br/>

We will end with a prompt like: __>__ <br/>


## SHOW DBs

We can cry for _help_, but we can ask for __show dbs__ too <br/>
<br/>

__using from nothing a DB__ <br/>

```mongo
use shopDB
```

_switched to db shopDB_ <br/>

The shpDB was created, but it needs to have information to be shown with __show dbs__ <br/>

__know current DB:__ <br/>

```mongo
db
```

## CREATE A COLLECTION (Table)

__COLLECTION = TABLE__ <br/>

Let's create the _products_ __collection__: <br/>

```mongo
db.products.insertOne({_id:1, name:"Pen", price:1.20})
```

## SHOW COLLECTIONS

```mongo
show collections
```

# QUERY

__search for id 1__ <br/>

```mongo
db.products.find({_id:1})
```

__search for all ids greater than 1__ <br/>

```mongo
db.products.find({_id:{$gt:1}})
```

__$gt__   greater than <br/>
__$gte__  greater or equal than <br/>
__$lt__   less than <br/>
__$lte__  less or equal than <br/>
__$ne__   not equal than <br/>
__$in__   any value in the array <br/>
__$nin__  none of the values in array <br/>


__search and show just ONE value from the row__ _(projection)_ <br/>

```mongo
db.products.find({_id:{$gt:1}}, {name:1})
```

__1 means true__ <br/>
__By default, always display our id, unless we especify false with a 0__ <br/>












