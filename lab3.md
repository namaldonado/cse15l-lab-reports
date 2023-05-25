# Researching Commands
## Command-line option 1 `-type` 
*Description:*
> The `-type` option allows you to search for files based on their type of file. It can be used to speficy the type of file to be searches, such as directories `d` or regular files `f`. Below we see the output of two examples. 


### **Here is the first example of this command line:**
```
find ./technical -type d
```

### **Here is the Output:**
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


### **Here is the second example of this command line:**
```
find ./technical -type f -name 1471-2091-2-13.txt
```

### **Here is the Output:**
```
./technical/biomed/1471-2091-2-13.txt 
```
Here we use the command line to find one regular file in the `./technical` directory! We could just write `find ./technical -type f`; this would list all the regular files, however for space purposes we'll just show one using the `-name` command. 

