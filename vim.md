# VIM

## ---MODES---

* Insert __i__
* Visual __v__
* Replace __R__
* Command __esc__

## ---BASIC---


### Save

>:w


### Quit

>:q


### Quit without asking

>:q!


### Save and quit

>:x


### Number of Lines

>:set nu


### Quit Number of Lines

>:set nu!


### u

>Undo


### ctrl + r

>Redo


### Block Vim

>ctrl+s

### Unblock Vim

>ctrl+q



## ---NAVIGATE---


### h

> move one character to the left


### j

> move one character up


### k

> move one character down


### l

> move one character to the right


### e

> moves forwards a word, sets cursor at the end of the word


### w

> moves forwards a word, sets cursor at the begining of the word


### b

> moves backwards a word


### gg

>to FIRST line


### Shift+g

>to last LINE


### gd

> Go to Definition


### gf

> Go to File


### ctrl+o

> return a buffer



## ---COPY, CUT AND PASTE---


### dd

>cut current row


### d2d

> cuts 2 rows


### dw

> cut the word, since the current character


### cw

> cut the word, and change to INSERT mode to change the word from current character


### diw

> cut the whole word, no matters where the cursor are, and change to INSERT mode. (delete inner word)


### p

>paste below current line


### shift+p

>paste above current line


### d2d

>cut 2 lines, and now we can paste them


### y3y

>copy 3 lines


### yw

>copy a word


### yy

>copy a line


## ---INSERT---


### o

>insert a blank line below current line

### shift+o

>insert a blank line above current line

### i

>insert text before current character

### a

>insert text AFTER current character

### shift+i

>insert text at the beginning of the line

### shift+a

>insert text at the END of the line



## ---DELETE---


### x

> deletes current character


### d3w

> deletes 3 words


### d$

> deletes the text in the current line from current character



## ---PLUGINS---

We have to install __plug__ <br/>

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Instalar __easymotion__ y __nerdtree__ <br/>











