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
   
    ` java String Server #### words.txt`


 3.  There is an issue with the file path in your "/save" section of the code
     your mistake lies in the 'else if(url.getPath().equals("/save"))' block. 
     Instead of using the actual this.path variable that holds the valid file path, 
     consider writing the file to a different path.
     
     
     `Files.write(Paths.get(this.path), toSave.getBytes());`

Another screenshot/terminal output showing 
what information the student got from trying
that, and a clear description of what the bug is.


At the end, all the information needed about the 
setup including:
- The file & directory structure needed
- The contents of each file before fixing the bug
- The full command line (or lines) you ran to trigger the bug
- A description of what to edit to fix the bug



You should actually set up and run the scenario 
from your screenshots. It should involve at 
least a Java file and a bash script. Describing 
the bug should involve reading some output at the 
terminal resulting from running one or more 
commands. Design an error that produces more 
interesting output than a single message about a 
syntax or unbound identifier error – showcase 
some interesting wrong behavior! Feel free to 
set this up by cloning and breaking some existing 
code like the grading script or code from class, 
or by designing something of your own from scratch, etc.



## Part 2 - Reflection
In a couple of sentences, describe something 
you learned from your lab experience in the 
second half of this quarter that you didn’t 
know before. It could be a technical topic we 
addressed specifically, something cool you 
found out on your own building on labs, 
something you learned from a tutor or classmate, 
and so on. It doesn’t have to be specifically 
related to a lab writeup, we just want to hear 
about cool things you learned!

