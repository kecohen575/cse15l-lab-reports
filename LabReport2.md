# Lab Report 2 - Servers and Bugs

> ## Part 1: Simplest Search Engine

Still in progress...

> ## Part 2: Debugging Process

Addressing the bug found in the reverseInPlace method in ArrayExamples.java:

```
  @Test
  public void testReverseInPlace4() {
    int[] input = {1,2,3,4,5};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{5,4,3,2,1}, input);
  }
 ```
 
 This test would result in {5,4,3,3,5} instead of the expected {5,4,3,2,1}. 
 
 After debugging the code looked like this:
 ```
 static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
 ```
 Two things were changed here: the for loop now runs over only the first half of the array and there is a temporary variable being used.
 
 Testing showed me that by changing the array it was running through it was losing elements it needed to access by the time it got to the end. 
 This was really confusing at first, so I had to run through the original code pretty thoroughly to see what was actually going wrong. 
 I added a temporary variable to keep track of elements so that they wouldn't be lost and changed two elements in one interation of the for loop rather   than one.
 Because of this, I also had to halve the amount of iterations of the loop.
 
 ---
 Still stuck on the ListTests part of the lab. Going to office hours soon for clarification.
