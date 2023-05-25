# Researching Commands                                          

> ***Before we begin there are a few things to note:
> I logged into cs15lsp23 account, changed the full path directory to stringsearch-data
> so all the examples below are from text files within this repository!*** 

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




--------
## Command-line option 2: `-iname`
*Description:*
> The `-iname` option is used to perform "case-insensitive" searches based on patterns. It allows us to find files and directories by their names. I think it's important to keep in mind, that it disregards the case of the letters. 


**1st Example:**
```
find ./technical -iname "*government*"
```


**Here is the Output:**
```
./technical/government
``` 
Here we find all directories in the `./technical` directory with names containing the phrase "government". This is a case-insensitive example. 


**2nd Example**
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
This is also a case-insensitive example. We could just leave the command as `find ./technical -name "*.txt" and that would list all files that end with .txt` however that wouldn't fit on the page so we'll use a smaller example. Here we find all the files in the `./technical` directory with names ending in "00.txt". 


We can also find files that are .png type files or even .pdf, however because our directory only contains txt files, we can only show a `.txt` example.  



---------
## Command-line option 3: `-size`
*Description:*
> The `-size` option allows us to search for files based on their size. We can specify the size of the files using different units ranging from bytes to megabytes and more. 


**1st Example**
```
find ./technical -size -2k
```


**Here is the Output:**
```
./technical/plos/pmed.0020191.txt
./technical/plos/pmed.0020226.txt
``` 

Here we find all files in the `./technical` directly less than 2 kilobytes. To signify that we want to find something less than 2 kilobytes we use the `-` sign and the letter `k` to signify kilobytes.  


**2nd Example**
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


Here we find all the files in the `./technical` directory more than 230k. Again same logic as above, with `+` representing more than and `k` representing kilobytes. There are other representations of sizes, for example megebytes can be represented with the letter `M`. 




---------
## Command-line option 4: `-exec`
*Description:*
> The `-exec` option allows us to execute a command on the files or directories found by `find`. We can do certain tasks such as copying/moving files or deleting files.  


**Here is the first example of using `-exec`:**

```
find ./technical -type d -exec readlink -f {} \;
```

Here we are findinf all directories in the `technical` directory and printing their absolute paths! 

For instance: The path `/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government` 
- represents the absolute file system path to the "government" directory located within the
"technical" directory
- further located in the "stringsearch-data" directory. 
- The full path indicates that the "stringsearch-data" directory is located in the user's home
directory. 

We can see this in the output below (line 4):


**Here is the Output:**



```
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/911report
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/biomed
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/About_LSC
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/Alcohol_Problems
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/Env_Prot_Agen
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/Gen_Account_Office
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/Media
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/government/Post_Rate_Comm
/home/linux/ieng6/cs15lsp23/cs15lsp23oe/stringsearch-data/technical/plos

``` 


**Here is the second example of using `-exec`:**


```
find ./technical -type f -exec rm {} \;
```



**Here is the Output:**


```
``` 

I decided to do this command last because it deletes all the regular files in the `./technical` directory. Hence there being no visible output. 


## Here are some links to sources I used to write this Lab Report: 

1. [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#links).

2. [Chat GPT - coming up with examples](https://openai.com/blog/chatgpt)

3. [Find Command in Linux - Formatting explanations](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

4. [GeeksforGeeks - '-name' and '-size'](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)
