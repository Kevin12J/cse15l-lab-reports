# Lab Report 2: Servers and SSH Keys
## Part 1 ChatServer
### Code
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String output="";

    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] arguments=url.getQuery().split("&");
            String[] messageArguments=arguments[0].split("=");
            String[] userArguments=arguments[1].split("=");
            if(messageArguments[0].equals("s")&&userArguments[0].equals("user")){
                output+=String.format("%s: %s\n", userArguments[1],messageArguments[1]);
            }
            else{
                return "wrong parameters";
            }
            return output;


        } else {
            return "404 Not Found!";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```
### Screenshot 1 (localhost:4000/add-message?s=Hi how are you?&user=Kevin)
![Image](/ChatServer1.png)

#### Methods Called
* `handleRequest(URI url)`: Takes in URI object as the paremeter.
* `.getPath()`: Method called on URI object to return the path of the URL as a String.
* `.contains("")`: Method called on String that returns true if the String in the paremeter is in the String that the method was called on. Otherwise it returns false.
* `.getQuery()`: Method called on URI object to return the query as a String.
* `.split("")`: Method called on String that takes a String as the parameter and splits the String into an array based on the parameter.
* `.equals("")`: Method called on Object that takes another Object as the parameter and returns true is the Object contents are equal. Otherwise it returns false. 
* `String.format("",...)`: Static method of the String class that returns a formatted String. It takes in a String containing format Strings and additional parameters for each format String. 

#### Values
* `String[] arguments`: `arguments` contains the String array `["s=Hi how are you?","user=Kevin"]` after the line `String[] arguments=url.getQuery().split("&");` runs
* `String [] messageArguments`: `messageArguments` contains the String array `["s","Hi how are you?"]` after the line `String[] messageArguments=arguments[0].split("=");` runs
* `String[] userArguments`: `userArguments` contains the String array `["user","Kevin"]` after the line `String[] userArguments=arguments[1].split("=");` runs
* `String output`: `output` contains the String `"Kevin: Hi how are you?\n"` after the line `output+=String.format("%s: %s\n", userArguments[1],messageArguments[1]);` runs

The field `output` in the `ChatServer` class was changed from `""` to `"Kevin: Hi how are you?\n"`.

### Screenshot 2 (localhost:4000/add-message?s=I am great thanks for asking!&user=Aaron)
![Image](/ChatServer2.png)

#### Methods Called
`handleRequest(URI url)`: Takes in URI object as the paremeter.
* `.getPath()`: Method called on URI object to return the path of the URL as a String.
* `.contains("")`: Method called on String that returns true if the String in the paremeter is in the String that the method was called on. Otherwise it returns false.
* `.getQuery()`: Method called on URI object to return the query as a String.
* `.split("")`: Method called on String that takes a String as the parameter and splits the String into an array based on the parameter.
* `.equals("")`: Method called on Object that takes another Object as the parameter and returns true is the Object contents are equal. Otherwise it returns false. 
* `String.format("",...)`: Static method of the String class that returns a formatted String. It takes in a String containing format Strings and additional parameters for each format String.

#### Values
* `String[] arguments`: `arguments` contains the String array `["s=I am great thanks for asking!","user=Aaron"]` after the line `String[] arguments=url.getQuery().split("&");` runs
* `String [] messageArguments`: `messageArguments` contains the String array `["s","I am great thanks for asking!"]` after the line `String[] messageArguments=arguments[0].split("=");` runs
* `String[] userArguments`: `userArguments` contains the String array `["user","Aaron"]` after the line `String[] userArguments=arguments[1].split("=");` runs
* `String output`: `output` contains the String `"Kevin: Hi how are you?\nAaron: I am great thanks for asking!\n"` after the line `output+=String.format("%s: %s\n", userArguments[1],messageArguments[1]);` runs

The field `output` in the `ChatServer` class was changed from `"Kevin: Hi how are you?\n"` to `"Kevin: Hi how are you?\nAaron: I am great thanks for asking!\n"`.

## Part 2 SSH Keys

### Private key
![image](/local.png)

### Public key
![image](/ieng6.png)

### Logging in
![image](/Login.png)

## Part 3 What I Learned
