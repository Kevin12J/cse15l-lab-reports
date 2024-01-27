# Lab Report 2: Servers and SSH Keys
## Part 1 ChatServer
# Code
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
