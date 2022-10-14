# Part1
## SearchEngine.java
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {

    ArrayList<String> list = new ArrayList<>();

    public String handleRequest(URI url) {
        ArrayList<String> substringList = new ArrayList<>();
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return parameters[1] +" " + "is added to the list";
                }
            }
            else if (url.getPath().contains("/search")){
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    for(String s: list){
                        if(s.contains(parameters[1])){
                            substringList.add(s);
                        }
                    }
                    String result = substringList.toString();
                    return result;
                }
            }
            return "404 Not Found!";
        }
}
  

class SearchEngine {
    public static void main(String[] args) throws IOException{
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```


![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-10-14%20at%204.20.26%20PM.png)
`handleRequest(URI url)` is called. 
The list is empty before the method call. After `handleRequest` is called, “anewstringtoaddd” is added to the list. 

![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-10-14%20at%204.21.33%20PM.png)
`handleRequest(URI url)` is called. 
The list contains “anewstringtoadd” before the method call. After `handleRequest` is called, “pineapple” is added to the list. 
![Image](https://github.com/catherineytf/cse15l-lab-reports/blob/main/Screen%20Shot%202022-10-14%20at%204.22.37%20PM.png)
`handleRequest(URI url)` is called. 
After adding some elements to list, list is now `[anewstringtoadd, pineapple, pineapple, apple, application]`. We search for strings that contain the substring “app”. The return value would be `[pineapple, pineapple, apple, application]`. 
If the strings in the method change, or the substring changes, the result would change as well. 





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

 
 


 
 
 
 
 
 






