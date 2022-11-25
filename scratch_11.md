### Task 1 (6kuy)
CamelCase Method 

Write simple .camelCase method (camel_case function in PHP, CamelCase in C# or camelCase in Java) for strings. All words must have their first letter capitalized without spaces. 

### Solution
```java
public class Solution {
    public static String camelCase(String str) {
        String[] str_1 = str.split(" ");
        String result = "";
        for(int i = 0; i < str_1.length; i++)
        {
           if(str_1[i].length() > 1){
              result += str_1[i].substring(0, 1).toUpperCase() + 
              str_1[i].substring(1).toLowerCase();
          }
          else{
            result += str_1[i].substring(0).toUpperCase();
          }
        }
        return result;
    }
}
```
### Favourite
```java
import org.apache.commons.lang3.text.WordUtils;

public class Solution {

    public static String camelCase(String str) {
      String result = ""; 
      for(String s : str.trim().split(" ")){
        result += WordUtils.capitalize(s);
      }
      return result;    
    }
}
```
[Task link](https://www.codewars.com/kata/587731fda577b3d1b0001196)
### Task 2 (6kuy)
Padovan numbers   
The Padovan sequence is the sequence of integers defined by the initial values
P(0) = P(1) = P(2) = 1
and the recurrence relation
P(n) = P(n-2) + P(n-3)
Your task is to write a method that returns nth Padovan number 
### Solution
```java
public class Solution {
  public static long padovan(int n) {
    var a = new long[n + 3];
    a[0] = 1;
    a[1] = 1;
    a[2] = 1;
    for (var i = 2; i < n; i++) {
      a[i + 1] = a[i - 1] + a[i - 2];
    }
    return a[n];
  }
}                
```
### Favourite
```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class Solution {
  
    private static List<Long> padovans = new ArrayList<>(Arrays.asList(1L, 1L, 1L));

    public static long padovan(int n) {
        for (int i = padovans.size(); i <= n; ++i) {
            padovans.add(padovans.get(i - 2) + padovans.get(i - 3));
        }

        return padovans.get(n);
    }
}
```
[Task link](https://www.codewars.com/kata/5803ee0ed5438edcc9000087)