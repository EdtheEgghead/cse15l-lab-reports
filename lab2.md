# Lab Report #2

## Part 1
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String string = new String();
    int count = 0;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format(string);
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if(parameters[0].equals("s")) {
                    if(count > 0){
                        string = string + "\n" + parameters[1];
                        count++;
                        return String.format(string);
                    }
                    string = string + parameters[1];
                    count++;
                    return String.format(string);
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
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
---
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-01-30%20at%201.33.26%20PM.png)
---
 1. To start the server you begin by compiling `StringServer.java` and `Server.java` with `javac Server.java StringServer.java` then typing `java StringServer 4000`
 2. When `java StringServer 4000` is typed into the terminal it runs `StringServer.java` with the command line argument of `4000` which creates a local server with a port number of `4000` by calling the `Server.start(int port, URLHandler handler)` with the first port argument as `4000` and the second argument as a new `Handler` object which comes from the `StringServer.java` class.
 3. Next, a HttpServer object is created with methods from the imported Http Libraries and an "create request entrypoint" is created for our server which uses the `handler` argument to create a method to deal with new quereies to our server. After this the server is started with `server.start();`
 4. After the server is started the `handleRequest` method in the `Handler` object that comes from `StringServer.java` handles queries to our local server. Inside the `Handler` object we have a string called `string` and an int called `count`. The latter two values are initialized to their default values(null and 0 respectively). `string` is where messages will be added and `count` keeps strack of how many times a value has been added.
 5. Upon the first new path being entered: `add-message?s=Hello TA or Tutor` `handleRequest` checks if the request begins with `/add-message`. If it has the desired path, it then splits the query into two arguments to validate if the first is equal to "s". If it does equal "s" then the `handleRequest` method checks if count is greater than zero. It makes this check to ensure that the first line on our webpage is formatted correctly because otherwise an additional `\n` adds an extra line before the text. If count is greater than zero then it adds the message after the equals sign and a new line to message in the server and increments count.
 6. If the URL's path equaled `/` then the current contents of string would be shown. If it did not equal either `/` or `/add-message` it returns "404 not found"
 7. After checking these conditions and adding the first parameter from `parameters` to `string`, count is incremented and the contents of `string` are displayed on the local server and our page now looks like the above screenshot.
 ---
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-01-30%20at%201.34.25%20PM.png)
 1. Since the server is already started we can skip the first four steps of the previous query and creation of server but, do note that currently `string = Hello TA or Tutor` and `count = 1`.
 2. Upon the new path being entered: `add-message?s=I just wanted to tell you that us students appreciate you and value you and your work!` `handleRequest` checks if the request begins with `/add-message`. If it has the desired path, it then splits the query into two arguments to validate if the first is equal to "s". If it does equal "s" then the `handleRequest` method checks if count is greater than zero. It makes this check to ensure that the first line on our webpage is formatted correctly because otherwise an additional `\n` adds an extra line before the text. If count is greater than zero then it adds the message after the equals sign and a new line to message in the server.
 3. If the URL's path equaled `/` then the current contents of string would be shown. If it did not equal either `/` or `/add-message` it returns "404 not found"
 4. After checking these conditions and adding the first parameter from `parameters` to `string`, count is incremented and the contents of `string` are displayed on the local server and our page now looks like the above screenshot.
---
## Part 2

## Part 3
  There are several things that I learned during week two and week three of lab. During week two, I learned how to launch a server on a remote server. Although I had previously run a server on my own computer during my own free time, I did not know that it was almost the same process to launch a server on a remote machine. In week three, I learned that a `.jar` file is just a bunch of classes zipped together. Though a small thing to learn, it brought continuity to an assignment in cse11 that had us using a provided `.jar` file to run several classes.
