# Lab Report 5: Putting it All Togetehr
## Part 1 - Debugging Scenario
### Original Post From Student
**Title:** Can't run Junit from terminal using testing script

**Message:**
I was working on a MathExamples class and implemented a factor method which returns an ArrayList of the factors of an integer. I created a few Junit tests that pass when I run them through VScode. However, when I run the testing script that I have, none of my tests will run, and I get an error. Here is the error message
```
TestFactor.java:1: error: package org.junit does not exist
import static org.junit.Assert.*;
                       ^
TestFactor.java:2: error: package org.junit does not exist
import org.junit.*;
^
TestFactor.java:10: error: cannot find symbol
  @Test
   ^
  symbol:   class Test
  location: class TestFactor
TestFactor.java:13: error: cannot find symbol
    assertEquals("check values",
    ^
  symbol:   method assertEquals(String,ArrayList<Integer>,ArrayList<Integer>)
  location: class TestFactor
TestFactor.java:21: error: cannot find symbol
    assertEquals("check values",
    ^
  symbol:   method assertEquals(String,ArrayList<Integer>,ArrayList<Integer>)
  location: class TestFactor
5 errors
Error: Could not find or load main class org.junit.runner.JUnitCore
Caused by: java.lang.ClassNotFoundException: org.junit.runner.JUnitCore
```
I have the following lines in `test.sh` to compile and run the tests by calling `bash test.sh` in the terminal
```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

javac -cp javac -cp $CPATH *.java

java -cp $CPATH org.junit.runner.JUnitCore TestFactor 
```
Here is the file structure of my code
```
lib/
  /hamcrest-core-1.3.jar
  /junit-4.13.2.jar
MathExamples.class
MathExamples.java
testFactor.class
TestFactor.java
test.sh
```
### Response From TA
Try and check what is stored in the `CPATH` variable in the bash script. You can also refer to the lecture 6 notes where we introduced Junit.
### Student Terminal Output After Suggestion
Thanks, I checked my `CPATH` variable and realized it was set to `'.:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar'`. I wrong path was used, and the correct path is `'.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'`. My tests were now able to run in my testing script.
```
JUnit version 4.13.2
.
Time: 0.003

OK (1 test)
```
### Information About The Setup That Was Needed
#### file and directory structure
```
lib/
  /hamcrest-core-1.3.jar
  /junit-4.13.2.jar
MathExamples.class
MathExamples.java
testFactor.class
TestFactor.java
test.sh
```
#### contents of the file
`test.sh` file contents:

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

javac -cp javac -cp $CPATH *.java

java -cp $CPATH org.junit.runner.JUnitCore TestFactor 
```
#### commands ran to trigger bug
`bash test.sh`
#### what to edit
The path in  the `CPATH` variable needed to be change in order to properly compile and run the Junit tests.

## Reflection
Something really helpful that I learned was about was using git in order to effectively colaborate with others on projects. I did use git prior to taking 15L, but I used it to simply backup my code. The lab experiences have taught me how to take advantage of the many other functionalities in git. For example, I learned about using branches in git which will be helpful for when I want to work on a seperate part of a project without impacting the main branch. Another useful tool that I learned in lab was the use of pull requests. Pull requests will be helpful for when I want to report bugs and offer potential fixes especially on open source projects. Learning git through lab has been very helpful, and I am excited to use it more in the future.
