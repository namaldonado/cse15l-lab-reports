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
### Failure-inducing input:
```
@Test
public void testReverseInPlace() {
  int[] arr = {1, 2, 3, 4, 5};
  ArrayExamples.reverseInPlace(arr);
  assertArrayEquals(new int[]{5, 4, 3, 2, 1}, arr);
}

```
- This test case will fail because the `reverseInPlace` method is not properly reversing the order of the input array. Instead, it is setting each element in the input array to the element at the corresponding index in the reversed array. 

### Input that doesn't induce a failure:

```
@Test
public void testAverageWithoutLowest() {
  int[] arr = {1, 2, 3};
  ArrayExamples.reverseInPlace(arr);
  assertArrayEquals(new int[] {3, 2, 1}, arr);
}

```

### Symptom
The failure-inducing input causes the `reverseInPlace` method to return an array with all zeros instead of the expected reversed array. 

### Before and After 
**Before**
```
static void reverseInPlace(int[] arr) {
  for (int i = 0; i < arr.length/2; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp; 
  }
}

```

**After**
```
static void reverseInPlace(int[] arr) {
  for (int i = 0; i < arr.length/2; i += 1) {
    int temp;
    temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp; 
  }
}

```
The fix addresses the issue by correctly assigning the reversed elements of the input array to the new array instead of overwriting the input array. The fixed method returns the new array instead of the input array. 

# Part 3
### Last Week I learned how to...
Last week I learned how to build and run a server! This was my frst introduction to understanding the basics of how URLs work. For example, I did not know how a localhost worked but after running servers on different computers, I realized that the localhost is basially the comptuer you are using running a certain Java program, which, during the lab's case, was using Server.java. After going further down the lab instructions I also learned how to make "search engines" where we could add strings or numbers to web server using paths and queries such as `/add?s=<stirng>` and   `/search?s=<string>`.  

