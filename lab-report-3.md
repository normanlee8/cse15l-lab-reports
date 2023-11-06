# Lab Report 3 - Norman Lee

## Part 1 - Bugs

* A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

```
 @Test
  public void testReversedInput() {
    int[] input1 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
```

* An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

Failure-inducing input:

![FII](lab3ss2.png)

Input that doesn't induce a failure:

![nonFail](lab3ss1.png)

* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

Before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The fix changes 'arr' to 'newArray' in the for loop so that it adds the elements in 'arr' into 'newArray' in reversed order and returns the 'newArray'.


## Part 2 - Researching Commands

grep -r

Example 1:
```
normanlee@Normans-MBP docsearch % grep -r "acute coronary syndrome " ./technical/biomed
./technical/biomed/1471-2121-3-11.txt:        anticoagulant [ 1 ] , acute coronary syndrome [ 4 ] ,
./technical/biomed/1468-6708-3-3.txt:        initiated early after an acute coronary syndrome in two
./technical/biomed/1468-6708-3-3.txt:        when initiated soon after an acute coronary syndrome will
./technical/biomed/1468-6708-3-3.txt:        acute coronary syndrome would be to accept the status quo,
./technical/biomed/1468-6708-3-3.txt:        an acute coronary syndrome will require confirmation. There
./technical/biomed/1468-6708-3-3.txt:        an acute coronary syndrome (ACS) at one year. If A-2-Z
./technical/biomed/1468-6708-3-3.txt:        within 10 days of an acute coronary syndrome and
```

Example 2:
```
normanlee@Normans-MBP docsearch % grep -r "acute coronary syndrome " ./technical/911report
normanlee@Normans-MBP docsearch % 
```

The -r option searches every file recursively in a directory and it is useful for finding a given string in a large database or large number of files.


grep -i

Example 1:
```
normanlee@Normans-MBP docsearch % grep -i "imagination" ./technical/911report/chapter-11.txt
            We believe the 9/11 attacks revealed four kinds of failures: in imagination, policy,
            IMAGINATION 
            We return to the issue of proportion-and imagination. Even Clarke's note challenging
            Institutionalizing Imagination: The Case of Aircraft as Weapons
            Imagination is not a gift usually associated with bureaucracies. For example, before
                exercise of imagination. Doing so requires more than finding an expert who can
            Considering what was not done suggests possible ways to institutionalize imagination.
                invasion. These policy challenges are linked to the problem of imagination we have
```

Example 2:
```
normanlee@Normans-MBP docsearch % grep -i "allhat" ./technical/biomed/1468-6708-3-7.txt
        (ALLHAT), the role of peripheral alpha-1 antagonists in the
        doxazosin arm of ALLHAT was stopped early, due to a
        cause CHF. Because ALLHAT is an active-control trial, no
        tolerability. In light of the results of ALLHAT, we
          alpha-1 antagonists. Among these, only ALLHAT
          ALLHAT demonstrated a highly statistically
          (RR 1.19, 95% CI 1.01-1.40). Since ALLHAT is a
          comparison, the rates of CHF in ALLHAT participants
          chlorthalidone has a similar risk reduction in the ALLHAT
        The report of the doxazosin arm termination in ALLHAT
        the ALLHAT trial were unexpected, given the potential
        Those treated with doxazosin in ALLHAT had a mean blood
        increasing the incidence of CHF in the ALLHAT trial, it
        failure findings in ALLHAT, the results support the current
```
The -i option ignores case-sensitivity and is useful for finding a given string without worrying about the case. It is useful for finding strings with various cases. 

grep -o

Example 1:
```
normanlee@Normans-MBP docsearch % grep -o "imagination" ./technical/911report/chapter-11.txt
imagination
imagination
imagination
imagination
imagination
```

Example 2:
```
normanlee@Normans-MBP docsearch % grep -o "Example" ./technical/biomed/1468-6708-3-4.txt
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
Example
```

The -o option only outputs the given string and is useful for isolating certain information.

grep -l

Example 1:
```
normanlee@Normans-MBP docsearch % grep -l "9/11" ./technical/911report/*
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
./technical/911report/preface.txt
```

Example 2:
```
normanlee@Normans-MBP docsearch % grep -l "acute coronary" ./technical/biomed/*
./technical/biomed/1468-6708-3-3.txt
./technical/biomed/1471-2121-3-11.txt
./technical/biomed/1472-6963-3-12.txt
./technical/biomed/1475-2891-2-1.txt
./technical/biomed/cvm-2-4-180.txt
./technical/biomed/cvm-2-4-187.txt
./technical/biomed/cvm-2-6-286.txt
```

The -l option outputs the files that have the given string, which is useful for finding files that contain the string.
