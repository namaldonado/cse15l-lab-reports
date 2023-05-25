# Researching Commands
## Command-line option 1 `-type` 
*Description:*
> The `-type` option allows you to search for files based on their type of file. It can be used to speficy the type of file to be searches, such as directories `d` or regular files `f`. Below we see the output of two examples. 


**Here is the first example of using `-type`:**
```
find ./technical -type d
```
**Here is the Output:**
```
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
Here we use the command-line to find all directories in the `./technical` directory! 


**Here is the second example of using `-type`:**
```
find ./technical -type f -name 1471-2091-2-13.txt
```
**Here is the Output:**
```
./technical/biomed/1471-2091-2-13.txt 
```
Here we use the command line to find one regular file in the `./technical` directory! We could just write `find ./technical -type f`; this would list all the regular files, however for space purposes we'll just show one using the `-name` command. 


## Command-line option 2: `-iname`
*Description:*
> The `-iname` option is used to perform "case-insensitive search" based on patterns. It allows us to find files and directories by their names. I think it's important to keep in mind, that it disregards the case of the letters. 

**Here is the first example of using `-iname`:**
```
find ./technical -iname "*government*"
```
**Here is the Output:**
```
./technical/government
``` 
Here we find all directories in the `./technical` directory with names containing the phrase "government". This is a case-insensitive example. 


**Here is the second example of using `-iname`:**
```
find ./technical -iname "*00.txt"
```
**Here is the Output:**
```
./technical/biomed/cc300.txt
./technical/government/Post_Rate_Comm/Gleiman_gca2000.txt      
./technical/plos/journal.pbio.0020100.txt
./technical/plos/journal.pbio.0020400.txt
./technical/plos/pmed.0020200.txt
``` 
Here we find all the files in the `./technical` directory with names ending in "00.txt". This is also a case-insensitive example. 



## Command-line option 3: `-size`
*Description:*
> The `-size` option allows us to search for files based on their size. We can specify the size of the files using different units ranging from bytes to megabytes and more. 

**Here is the first example of using `-size`:**
```
find ./technical -size -2k
```
**Here is the Output:**
```
./technical/plos/pmed.0020191.txt
./technical/plos/pmed.0020226.txt
``` 
Here we find all files in the `./technical` directly less than 1k.  


**Here is the second example of using `-size`:**
```
find ./technical -size +230k
```
**Here is the Output:**
```
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/d01591sp.txt
``` 
Here we find all the files in the `./technical` directory more than 230k



