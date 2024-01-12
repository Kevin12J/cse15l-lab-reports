# Lab Report 1: Remote Access and FileSystem
## `cd` command
### no arguments
run the `cd` command with no arguments in the directory `/home`
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
nothing happens when using cd with no arguments and the directory is still `/home`
### directory as argument
run the `cd` command as `cd lecture1` in the directory `/home`
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
the directory is set to `/home/lecture1` and the prompt changes
### file as argument
run the `cd` command as `cd Hello.java` in the directory `/home/lecture1`
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```
the output is `bash: cd: Hello.java: Not a directory` and this is an error because `cd` had a file used as an argument instead of a directory
***
## `ls` command
### no arguments
run the `ls` command with no arguments in the directory `/home`
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ 
```
the output is the contents in the `/home` directory which is just another directory
### directory as argument
run the `ls` command as `ls lecture1` in the directory `/home`
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$ 
```
the output is the contents in the `\home\lecture1` directory 
### file as argument
run the `ls` command as `ls Hello.java` in the directory `/home/leceture1'
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
[user@sahara ~/lecture1]$ 
```
the output is the file put as the argument with the `ls` command
***
## `cat` command
### no arguments
### directory as argument
### file as argument
