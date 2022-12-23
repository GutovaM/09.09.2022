### Task 1 (6kuy)
Find The Parity Outlier       
You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier" N.
### Solution
```java
public class FindOutlier{
  static int find(int[] integers){
   int p = 0;
   for(int i = 0; i < integers.length && i < 3; i++){
    if(integers[i] % 2 == 0){
        p++;
      }
   }
    if(p >= 2){
      for(int i = 0; i < integers.length; i++){
        if(integers[i] % 2 != 0){
          return integers[i];
        }
      }
    }
    else{
      for(int i = 0; i < integers.length; i++){
          if(integers[i] % 2 == 0){
            return integers[i];
          }
        }
    }
    return 0;
  }
} 
```
### Favourite
```java
public class FindOutlier{
  static int find(int[] integers) {
        int even = 0;
        int odd = 0;
        int cycle = 0;

        for(Integer value : integers) {
            if(value % 2 == 0) {
                cycle++;
                even = value;
            }else {
                odd = value;
            }
        }
        return (cycle > 1) ? odd : even;
    }
}
```
[Task link](https://www.codewars.com/kata/5526fc09a1bbd946250002dc)
### Task 2 (6kuy)
Split Strings                    
Complete the solution so that it splits the string into pairs of two characters. If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('_').   
### Solution
```java
public class StringSplit {
    public static String[] solution(String s) {
      int l = s.length();
      if(s.length() % 2 != 0) {
        s = s + "_";
        l = l + 1;
        }
      String[] arr = new String[s.length() / 2];
      int x = 0;
      for(int i = 0; i < s.length() - 1; i = i + 2){
        arr[x++] = s.substring(i,i+2);
      }
      return arr;
    }
} 
```
### Favourite
```java
public class StringSplit {
    public static String[] solution(String s) {
        s = (s.length() % 2 == 0)?s:s+"_";
        return s.split("(?<=\\G.{2})");
    }
}
```
[Task link](https://www.codewars.com/kata/515de9ae9dcfc28eb6000001)