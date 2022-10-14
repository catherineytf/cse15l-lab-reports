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

![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-10-14%20at%2012.37.13%20PM.png)

**The bug:**

Original code:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
Fixed code:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
We should change the code in the for loop. It should be `newArray[i] = arr[arr.length-i-1]`, so that the code is actually updating the values in the newArray. We should also return `newArray` instead of `arr`. 

**The connection between the symptom and the bug**

The original code works to update the elements in `arr` and return `arr`. Every element in `newArray` is 0 when we create the `newArray`. So the for loop basically updates every element in `arr` to 0. That’s why the symptom shows that the first element in the actual result is 0 while it is supposed to be 9. 

## ListExamples.java
**The failure-inducing input:**
```
@Test
   public void testFilter(){
      StringChecker ls = new LongString();
      ArrayList<String> input = new ArrayList<>();
      input.add("apple");
      input.add("banana");
      input.add("pear");
      input.add("strawberry");
      input.add("blackberry");
      ArrayList<String> expected = new ArrayList<>();
      expected.add("banana");
      expected.add("strawberry");
      expected.add("blackberry");
      assertEquals(expected,ListExamples.filter(input, ls));
   }
 ```
 **The symptom:**
 
 ![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-10-14%20at%201.14.23%20PM.png)
 
 **The bug:**
 
 Original code:
 ```
 static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0,s);
      }
    }
    return result;
  }
 ```
 The original code adds every new element to the front of the list, instead of the end of the list.

 Fixed code:
  ```
 static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
 ```
 `result.add(s)` makes sure that every element is added to the end of the list. 
 
 **The connection between the symptom and the bug**

Because the original code adds elements to the front of the list, the order of elements in the actual result does not match with the order of elements in the expected result. 

 
 


 
 
 
 
 
 






