# Part 1

### Here is the code for StringServer
```
import java.io.IOException;
import java.net.URI;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;

class StringHandler implements URLHandler {
  List<String> lines;
  String path;
  StringHandler(String path) throws IOException {
    this.path = path;
    this.lines = Files.readAllLines(Paths.get(path));
  }
  public String handleRequest(URI url) throws IOException {
    String query = url.getQuery();
    if(url.getPath().equals("/add")) {
      if(query.startsWith("s=")) {
        String toAdd = query.split("=")[1];
        this.lines.add(toAdd);
        return;
      } else {
        return "/add requires a query parameter s\n";
      }
    } else {
      return String.join("\n", lines) + "\n";
    }
    
  }
}

// USE NumberServer.java as template for below
// === ==== ==== === ==== 
class StringServer {
  public static void main(String[] args) throws IOException {
    if(args.length == 0){
      System.out.println("Missing port number! Try any number between 1024 to 49151");
      return;
    }
    if(args.length == 1){
      System.out.println("Missing file path!);
      return;
    }

    int port = Integer.parseInt(args[0]);

    Server.start(port, new StringHandler(args[1]));
  }
}

```
### And below are two screenshots of using /add-message:

<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-10%20221708.png"  width="800"/>

`/add-message?s=Hello`
For the first request, the relevant argument is the **URI**. The path field of the **StringHandler** instance is the file path passed as an arugment when the **StringHandler** instance was created. The **lines** field of the **StringHandler** is a list of stirngs representing the lines of the file specifiec by the file path. The **handleRequest** method chesks if the path of the URL is `/add` and if the query string starts with **"s="**. The only reason why the certain **list** would not get changed if the iput failed to contain either the path or correct query string.

<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-10%20220906.png"  width="800"/>
`/add-message?s=HelloWorld`
For the second request, the relevant argument stays the same. The **path** and **lines** fields of the **StringHolder** instance are the same as before. The **handleRequest** method checks if the path and query string satisfy the conditions as mentioned aobve. In this case, since both conditions are satisfied, the method extracts the string to add from the query string and *appends* it to the list of lines. Afterwards we have the result:


```
Hello
HelloWorld
```


# Part 2
Choose one of the bugs from lab 3.
### ArrayExamples Bug 


Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)


One possible input that can cause a failure is an array with an odd number of elements in the reverseInPlace method. For example, consider the input array {1, 2, 3, 4, 5}. The expected output after calling reverseInPlace should be {5, 4, 3, 2, 1}. However, due to a logic error in the method, the output will be {1, 4, 3, 2, 5}. The error is caused by the fact that the method swaps elements from both ends of the array, but since the loop iterates over half of the array, the middle element is not swapped and remains in place. To fix this, the loop should iterate over the entire array, and swap the current element with its corresponding element from the end of the array.

One possible input that does not induce a failure is an empty array in the averageWithoutLowest method. Since an empty array has no elements, the method returns 0.0, which is the correct result. Similarly, an array with just one element will also return 0.0.


The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.




# Part 3
### Last Week I learned how to...
Last week I learned how to build and run a server! This was my frst introduction to understanding the basics of how URLs work. For example, I did not know how a localhost worked but after running servers on different computers, I realized that the localhost is basially the comptuer you are using running a certain Java program, which, during the lab's case, was using Server.java. After going further down the lab instructions I also learned how to make "search engines" where we could add strings or numbers to web server using paths and queries such as `/add?s=<stirng>` and   `/search?s=<string>`.  
