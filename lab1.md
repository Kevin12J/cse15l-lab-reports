# Lab Report 1: Remote Access and FileSystem
## `cd` command
### no arguments
Call the `cd` command with no arguments in the directory `/home`
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
Using the `cd` command with no arguments will go back to the home directory so the directory remains the same since `cd` was called in `/home`. If `cd` was called in the `/home/lecture1` directory, then the directory will change from `/home/lecture1` to `/home`.

### path to directory as argument
Call the `cd` command as `cd lecture1` in the directory `/home`
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
Using the `cd` command with a directory as an argument will change the directory to the directory in the argument. The directory was set to `/home/lecture1/` since `cd lecture1` was called in the `/home` directory. If `cd lecture1/messages` was called in the `/home` directory, then the directory would be set to `/home/lecture1/messages`. An error messgae will appear if the directory in the argument doesn't exist.
### path to file as argument
Call the `cd` command as `cd /lecture1/Hello.java` in the directory `/home`
```
[user@sahara ~]$ cd /lecture1/Hello.java
bash: cd: /lecture1/Hello.java: No such file or directory
[user@sahara ~]$ 
```
Using the `cd` commad with a path to a file as an argument will result in an error. The output was `bash: cd: /lecture1/Hello.java: No such file or directory` because the file `Hello.java` was used as the argument with the `cd` command, and `Hello.java` is not a directory.
## `ls` command
### no arguments
Call the `ls` command with no arguments in the directory `/home`
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ 
```
Using the `ls` command with no arguments will return the contents of the current directory. The directory `lecture1` was returned since `lecture1` was the directory inside `/home`. If `ls` was called in the directory `/home/lecture1` the output would be `Hello.class  Hello.java  messages  README` as those were the contents in the `/home/lecture1` directory. 
### path to directory as argument
Call the `ls` command as `ls lecture1` in the directory `/home`
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$ 
```
Using the `ls` command with a directory as an argument will result in the contents of the specified directory being returned. `Hello.class  Hello.java  messages  README` was returned as they were in the directory `/home/lecture1`. An error message will appear if the directory used as the argument is not found.
### path to file as argument
Call the `ls` command as `ls lecture1/Hello.java` in the directory `/home'
```
[user@sahara ~]$ ls lecture1/Hello.java
lecture1/Hello.java
[user@sahara ~]$ 
```
Using the `ls` command with a path to a file as an argument will return the path to the file in the argument. The output was `lecture1/Hello.java` when calling `ls lecture1/Hello.java`. If you use a file that doesn't exist it will result in an error message. For example calling `ls bye.java` will result in the output `ls: cannot access 'bye.java': No such file or directory`.
## `cat` command
### no arguments
Call the `cat` command with no arguments in the directory `/home`
```
[user@sahara ~]$ cat
hello
hello
world
world
^C
[user@sahara ~]$ 
```
Using the `cat` command with no arguments will place the terminal in a state where each user input is repeated back. There is no intial output but the user can type in different things and have them outputed again. The user can exit this state by pressing [ctrl]+[c].
### path to directory as argument
Call the `cat` command as `cat lecture1` in the directory `/home'
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$
```
Using the `cat` command with a directory as an argument will result in an error. The output was `cat: lecture1: Is a directory` since a directory was used an argument.
### path to file as argument
Call the `cat` command as `cat lecture1/Hello.java` in the directiory `/home`
```
[user@sahara ~]$ cat lecture1/Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~]$
```
Using the `cat` command with a path to a file as the argument will print out the contents of the file. The contents of multiple files can be shown by using additional arguments as shown with calling `cat en-us.txt es-mx.txt` in the `/home/lecture1/messages` directory. If you use a file that doesn't exist it will result in an error. For example calling `cat lecture1/bye.java` will result in the output `cat: lecture1/bye.java: No such file or directory`.
