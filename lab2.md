# Part 1


# Part 2
Choose one of the bugs from lab 3.
## ArrayExamples Bug 


Provide:

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)


One possible input that can cause a failure is an array with an odd number of elements in the reverseInPlace method. For example, consider the input array {1, 2, 3, 4, 5}. The expected output after calling reverseInPlace should be {5, 4, 3, 2, 1}. However, due to a logic error in the method, the output will be {1, 4, 3, 2, 5}. The error is caused by the fact that the method swaps elements from both ends of the array, but since the loop iterates over half of the array, the middle element is not swapped and remains in place. To fix this, the loop should iterate over the entire array, and swap the current element with its corresponding element from the end of the array.

One possible input that does not induce a failure is an empty array in the averageWithoutLowest method. Since an empty array has no elements, the method returns 0.0, which is the correct result. Similarly, an array with just one element will also return 0.0.


The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.




# Part 3
# Last Week I learned how to...
Last week I learned how to build and run a server! This was my frst introduction to understanding the basics of how URLs work. For example, I did not know how a localhost worked but after running servers on different computers, I realized that the localhost is basially the comptuer you are using running a certain Java program, which, during the lab's case, was using Server.java. After going further down the lab instructions I also learned how to make "search engines" where we could add strings or numbers to web server using paths and queries such as "/add?s=<stirng>" and "/search?s=<string>".  
