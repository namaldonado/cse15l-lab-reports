# Lab Report 4
## Log into ieng6
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20185749.png"/>

Keys Pressed: `<s><s><p><space><c><s><1><5><l><s><p><2><3><o><e><shift><2><i><e><n><g><6><.><u><c><s><d>.<e><d><u>`
These are just a few chaaracters I used to write the following result in the command line.

```
ssh cs15lsp23oe@ieng6.ucsd.edu
******************
```

## Clone your fork of the repository from your Github account 
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20185902.png"/>
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20190023.png"/>

I had already copied the URL beforehand.
Keys Pressed: `<g> <i> <t> <space> <c> <l> <o> <n> <e> <space> <ctrl> <v> <enter>`
...

```
git clone https://github.com/namaldonado/lab7
```

## Run the tests, demonstrating that they fail
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20191945.png"/>

Keys Pressed: `<l><s><enter> <c><d><space><l><a><b><7><enter> <l><s><enter> <s><h><space><t><e><s><t><.><s><h>`
> I wanted to see what files were under my current working directory so I input `ls`.
> I then changed the working directory to lab7 using the `cd` command.
> Afterwards I checked the files under the lab7 directory.

I input sh test.sh to execute the ListExamples.java file, and it gave an output such as the one shown in the photo above. 

```
ls
cd lab7
ls
sh test.sh
```

## Edit the code file `ListExamples.java` to fix the failing test (as a reminder, the error in the code is just that `index1` is used instead of `index2` in the final loop in merge)
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20191920.png"/>

Keys Pressed: `<v><i><m> <shift><l><i><s><t><shift><e><x><a><m><p><l><e><s><.><j><a><v><a> <enter>`
```
vim ListExamples.java
```
With the keys pressed shown above, I would be able to access the file ListExamples through vim. 


Keys Pressed:
```
<j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j><j>
<l><l><l><l><l><l><l><l><l><l><l> 
<x><i><2> <esc><:><w><q><enter>
```

I decided to continue practicing with the `h`, `j`, `k`, `l` keys. I started off at the first letter of the first line so I had to go down 44 keys and 11 to the right. I then deleted replaced the number 1 with the number 2 and saved then exited out of vim. 

## Run the tests, demonstrating that they need now succeed
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20192615.png"/>

Keys Pressed: `<s><s><h><space><t><e><s><t><.><s><h><enter>`


This is the same line written before that was used to show that the test failed. The Shell goes through the files until it finds test.sh and then runs the file.


## Commit and push the resulting change to your Github account
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20192957.png"/>
<img src="https://raw.githubusercontent.com/namaldonado/cse15l-lab-reports/main/Screenshot%202023-05-22%20193108.png"/>

Keys Pressed: `<g><i><t><space><c><o><m><m><i><t><space><-><a><enter><i>`

I then wrote in a message for the commit: //committed! changed index1 to index2, and afterwards I press the following keys:

Keys Pressed: `<esc><enter> <:><w><q>`
This exits us out of the editor for the message and adds the changes to the file text ListExamples. 

To push the file, I press the following keys:
Keys Pressed: <g><i><t><space><p><u><s><h>
  
 
  
