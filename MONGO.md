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

## run

In Terminal Type: mongod <br/>

If launchs an SocketException Error: Address already in use, check old instance:

```terminal
sudo lsof -iTCP -sTCP:LISTEN -n -P
```
Then kill process:

```terminal
sudo kill ###
```

Where _###_ is the PID. <br/>














