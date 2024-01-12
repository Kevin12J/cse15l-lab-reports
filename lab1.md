# Lab Report 1: Remote Access and FileSystem
## `cd` command
### no arguments
run the `cd` command with no arguments in the directory `/home`
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
Using the `cd` command with no arguments will go back to the home directory so the directory remains the same since `cd` was called in `/home`. If `cd` was called in the `/home/lecture1` directory, then the directory will change from `/home/lecture1` to `/home`.

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
## `cat` command
### no arguments
run the `cat` command with no arguments in the directory `/home`
```
[user@sahara ~]$ cat
hello
hello
world
world
^C
[user@sahara ~]$ 
```
There is no intial output but the user can type in different things and have them outputed again. The user can exit this state by pressing [ctrl]+[c].
### directory as argument
run the `cat` command as `cat lecture1` in the directory `/home'
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$
```
the output is `cat: lecture1: Is a directory` and this is an error because `cat` had a directory used as an argument
### file as argument
run the `cat` command as `cat Hello.java` in the directiory `/home/lecture1`
```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~/lecture1]$ 
```
the output is the contents in the `Hello.java` file
