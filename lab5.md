# Lab Report 5
## Part 1 - Debugging Scenario 

<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20211436.png"  width="600"/>

-----------------------
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
<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213156.png"  width="600"/>


<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213242.png"  width="600"/>


<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213253.png"  width="600"/>


<img src= "https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-06-05%20213323.png"  width="600"/>






## Part 2 - Reflection
There are a lot of things I learned during this course, but the most memorable topic I learned was handling text files. Such as counting and finding files. There was something really cool about knowing how a single file can hold multiple files, and how a single command line can find an exact number of files containing certain characters or finding a spceific file from a bunch of similarly structued files. A cool thing I learned during this course was how long you could stay in the CS building labs and findind all the cool lounges around top floors of the CS buildings. 
