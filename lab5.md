# Lab Report 5
## Part 1 - Debugging Scenario 

<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20211436.png"  width="400"/>

-----------------------
### My Suggestions
 Hi! Here are a few suggestions I would consider:
 
 1. Consider compiling your files in the following manner:


     `javac Server.java StringServer.java`
     
     
     
 2. You are missing a file path
     A file path can be as simple as a text file which in this case is words.txt
     you were heading in the right direction, you just needed to consider the other
     files in the stringsearch directory (you can do with with the ls command)
   
    ` java String Server #### words.txt `


 3.  There is an issue with the file path in your "/save" section of the code
     your mistake lies in the 'else if(url.getPath().equals("/save"))' block. 
     Instead of using the actual this.path variable that holds the valid file path, 
     consider writing the file to a different path.
     
     
     `Files.write(Paths.get(this.path), toSave.getBytes());`


### Students Output:

This image shows the student compiling the Server. We can see it is successful because it generated a link to a server. 
<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213156.png"  width="600"/>



Here the student tests the code to see if adding a word in the text file `words.txt` works. Which we can see in the image below worked. 
<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213242.png"  width="600"/>



Here the student tests the code again to see if they can save the word added. We see the message "saved!" so we can guarantee that our code worked, which is great because this was a snippet from the code we caught a slight bug. 
<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213253.png"  width="600"/>



Here the student tests the search command and it works successfully as well, concluding the code and Server ran smoothly. 
<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213323.png"  width="600"/>



### Necessary Information

I cloned the repository *stringsearch* from github onto the terminal in Visual Studio Code.
Server.java was actually the server I tried to do for a lab report from before. 
It had failed so it was perfect for a scneario that needed fixing. 
A few command lines that I ran are as follows: 
```
ls 
cd string search
ls
javac Server.java StringServer.java
java StringServer 4909 words.txt
```

Here was the change in code necessary for it to run:



<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20215241.png"  width="600"/>




## Part 2 - Reflection
There are a lot of things I learned during this course, but the most memorable topic I learned was handling text files. Such as counting and finding files. There was something really cool about knowing how a single file can hold multiple files, and how a single command line can find an exact number of files containing certain characters or finding a spceific file from a bunch of similarly structued files. A cool thing I learned during this course was how long you could stay in the CS building labs and findind all the cool lounges around top floors of the CS buildings. 
