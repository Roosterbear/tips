# WINDOWS TRICKS ===========================================================================================================

## SCREENSHOT

* __win+shift+s__

## TASK MANAGER

* __ctrl+shift+esc__

## BAT (Command Line)

__@echo off__<br/>
- Removes the execution line of the command.
- If you want your script to look professional, is mandatory.

__pause__
- Use pause to stop the execution of a script and waits the user response.

__pause>nul__
- We hide the message "Presiona una tecla para continuar..."

__start__
- Opens files, web sites, etc.

__color__ [background][text]<br/>
The most used is 0F or 0A<br/>

| Code | Color |
| :---: | :---: |
| 0 | black | 
| 1 | blue |
| 2 | aquamarine |
| 3 | red |
| 4 | purple |
| 5 | yellow |
| 6 | black |
| 7 | white-gray |
| 8 | grey |
| 9 | light blue |
| A | light green |
| B | light aquamarina |
| C | light red |
| D | light purple |
| E | light yellow |
| F | white white |


### Tip #1 _hide a folder_

_invisible_ <br/>
>attrib +h +s +r foldername

_visible_ <br/>
>attrib -h -s -r foldername

### Tip #2 _history_

>doskey /history


### Tip #3 _change color_

>color 07
>color /?

### Tip #4 _change prompt and title_

>prompt hacker$G
>prompt beautiful hacker$G
>title Hackers

_return original_ <br/>

>prompt

