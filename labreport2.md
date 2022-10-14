# Part2
## ArrayExamples.java
**The failure-inducing input:**
```
 @Test
 public void testReversed2(){
   int[] input = {1,3,4,5,6,9};
   assertArrayEquals(new int[]{9,6,5,4,3,1}, ArrayExamples.reversed(input));
 }
 ```
**The symptom:**



