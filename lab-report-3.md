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


## Part 2 - Researching Commands
