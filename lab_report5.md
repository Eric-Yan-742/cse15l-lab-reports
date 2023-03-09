# Lab Report 6: Grading Script Demo

- This is the code of my grading script

```bash
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf *.class
rm -rf testResult.txt # Delete all files cloned before

git clone $1 student-submission
echo 'Finished cloning'
if [[ -f "student-submission/ListExamples.java" ]]
then
    echo "File is found!"
else
    echo "Cannot find ListExamples.java!"
    exit 1
fi
cp student-submission/ListExamples.java .
javac -cp $CPATH *.java
if [[ $? -ne 0 ]]
then
    echo "Compile error"
    exit 2
fi
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > testResult.txt
RESULT=`grep "failure" testResult.txt`
if [[ $RESULT == "" ]]
then
    echo "Tests all Pass" # If tests all pass
else
    echo `grep "Failures:" testResult.txt` # If any of the tests fail
fi
```

- To use the grading script, use the command `bash grade.sh <gitrepo_url>`
- Generally speaking, the script deletes all previous cloned files and clone the target repository into a directory called "student-submission". Then, if the name of the file is not "ListExamples.java" or there's a compiler error, the script will print an error message and exit. If the file is found and compiled, Junit tests in the file "TestListExamples.java" will be used to test the implementation of "ListExamples.java". Complete output of Junit will be stored in "testResult.txt". The script will print the number of tests passed and the number of tests failed.
- **StringChecker** and **TestListExamples** class (in TestListExamples.java)

```java
class IsMoon implements StringChecker {
  public boolean checkString(String s) {
    return s.equalsIgnoreCase("moon");
  }
}

public class TestListExamples {
  @Test(timeout = 500) //Used to check merge method
  public void testMergeRightEnd() {
    List<String> left = Arrays.asList("a", "b", "c");
    List<String> right = Arrays.asList("a", "d");
    List<String> merged = ListExamples.merge(left, right);
    List<String> expected = Arrays.asList("a", "a", "b", "c", "d");
    assertEquals(expected, merged);
  }
  @Test
  public void testFilter() { //Used to check filter method
    List<String> filtered1 = new ArrayList<>(Arrays.asList("abc", "moon", "def"));
    List<String> filtered2 = new ArrayList<>(Arrays.asList("moon", "moon", "moon"));
    StringChecker sc = new IsMoon(); 
    List<String> actual_result1 = ListExamples.filter(filtered1, sc);
    List<String> actual_result2 = ListExamples.filter(filtered2, sc);
    assertEquals(Arrays.asList("moon"), actual_result1);
    assertEquals(Arrays.asList("moon", "moon", "moon"), actual_result2);
  }
}
```

## File not found demo

### Example

- [Repo](https://github.com/ucsd-cse15l-f22/list-methods-filename)
- The repository contains a file called "ListMethods.java". It doesn't match the expected file name "ListExamples.java"
- Here's the output after running the script.

    ```text
    09:42 PM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-filename
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Receiving objects: 100% (3/3), done.
    Finished cloning
    Cannot find ListExamples.java!
    ```

- The script cannot find the file since the file has the wrong name. As a result, "Cannot find ListExamples.java" is printed, and the script exits.

## Compiler error demo

### Example 1

- [Repo](https://github.com/ucsd-cse15l-f22/list-methods-compile-error)
- The repository contains a file called "ListExamples.java". The file misses a semicolon at line 15.
- Output:

    ```text
    10:03 PM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-compile-error
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Receiving objects: 100% (3/3), done.
    Finished cloning
    File is found!
    ListExamples.java:15: error: ';' expected
            result.add(0, s)
                            ^
    1 error
    Compile error
    ```

- As we can see, the file is found this time. However, due to the syntax error, the script detects the compile error. It prints displays the error message of java, prints "Compile error", and exits.

### Example 2

- [Repo](https://github.com/ucsd-cse15l-f22/list-methods-signature)
- The repository contains a file called "ListExamples.java". The method "filter" in the file has the wrong order of parameters.
- Output

    ```text
     09:50 AM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-signature
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 3
    Receiving objects: 100% (3/3), done.
    Finished cloning
    File is found!
    TestListExamples.java:28: error: incompatible types: List<String> cannot be converted to StringChecker
        List<String> actual_result1 = ListExamples.filter(filtered1, sc);
                                                        ^
    TestListExamples.java:29: error: incompatible types: List<String> cannot be converted to StringChecker
        List<String> actual_result2 = ListExamples.filter(filtered2, sc);
                                                        ^
    Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
    2 errors
    Compile error
    ```

- Because the order of parameter is wrong, when the Junit test attempts to pass the argument in the expected order to "filter", arguments and parameter type mismatch. Thus, a compile error occurs. The script detects the error, shows part of the error message thrown by java, prints "Compile error" at the end, and exit.

## Failed Tests demo

### Example 1

- [Repo](https://github.com/ucsd-cse15l-f22/list-methods-lab3)
- The repository contains a file called "ListExamples.java". There is a bug in the "merge" method in the file. At line 43, index1 is incremented instead of index2, which causes an infinite loop.
- Output

    ```text
    10:24 PM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-lab3
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Receiving objects: 100% (3/3), done.
    Finished cloning
    File is found!
    Tests run: 2, Failures: 1
    ```

- File is found, compiled, runned successfully this time. The script displays the number of tests passed and failed. Meanwhile, the script creates a new text file called "testResult.txt" in the same directory as "grade.sh" and store the complete Junit output there

- Content of "testResult.txt"

    ```text
    JUnit version 4.13.2
    .E.
    Time: 0.643
    There was 1 failure:
    1) testMergeRightEnd(TestListExamples)
    org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at java.base@17.0.5/java.util.Arrays.copyOf(Arrays.java:3512)
        at java.base@17.0.5/java.util.Arrays.copyOf(Arrays.java:3481)
        at java.base@17.0.5/java.util.ArrayList.grow(ArrayList.java:237)
        at java.base@17.0.5/java.util.ArrayList.grow(ArrayList.java:244)
        at java.base@17.0.5/java.util.ArrayList.add(ArrayList.java:454)
        at java.base@17.0.5/java.util.ArrayList.add(ArrayList.java:467)
        at app//ListExamples.merge(ListExamples.java:42)
        at app//TestListExamples.testMergeRightEnd(TestListExamples.java:19)

    FAILURES!!!
    Tests run: 2,  Failures: 1
    ```

- The Junit output shows that "testMergeRightEnd" fails because "test timed out after 500 milliseconds". It is due to the infinite while loop in the "merge" method, exactly the same as what we expect.

### Example 2

- [Repo]( https://github.com/ucsd-cse15l-f22/list-examples-subtle)
- The repository contains a file called "ListExamples.java". There are subtle bugs in "filter" and "merge" methods.
- Output

    ```text
    10:41 PM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh  https://github.com/ucsd-cse15l-f22/list-examples-subtle
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Receiving objects: 100% (3/3), done.
    Finished cloning
    File is found!
    Tests run: 2, Failures: 2
    ```

- We can see both tests fail. It indicates both "filter" and "merge" have bugs.

- Content of "testResult.txt"

    ```text
    JUnit version 4.13.2
    .E.E
    Time: 0.009
    There were 2 failures:
    1) testMergeRightEnd(TestListExamples)
    java.lang.AssertionError: expected:<[a, a, b, c, d]> but was:<[a, b, c, d]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at TestListExamples.testMergeRightEnd(TestListExamples.java:21)
    2) testFilter(TestListExamples)
    java.lang.AssertionError: expected:<[moon]> but was:<[moon, moon, moon]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at TestListExamples.testFilter(TestListExamples.java:30)

    FAILURES!!!
    Tests run: 2,  Failures: 2
    ```

- The complete output of Junit shows the details of bugs. We can see that the script detects all the subtle bugs in "ListExamples.java".

## Tests all pass demo

### Example

- [Repo](https://github.com/ucsd-cse15l-f22/list-methods-corrected)
- The repository contains a file called "ListExamples.java". It has all subtle bugs corrected. Thus, this repo should get full credit
- Output

    ```text
    09:50 AM ericyan ~/CSE/CSE15L/lab6/list-examples-grader (main)$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected
    Cloning into 'student-submission'...
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Compressing objects: 100% (2/2), done.
    Receiving objects: 100% (3/3), done.
    remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
    Finished cloning
    File is found!
    Tests all Pass
    ```

- As we expect, correct implementation does pass all the tests. 
- Content of "testResult.txt"

    ```text
    JUnit version 4.13.2
    ..
    Time: 0.007

    OK (2 tests)
    ```

- The script also captures the complete output of Junit Test successfully. 