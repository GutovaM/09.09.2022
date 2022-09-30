### Task 1 (7kuy)
Sum of the first nth term of Series                                                                                              Your task is to write a function which returns the sum of following series upto nth term(parameter).

Series: 1 + 1/4 + 1/7 + 1/10 + 1/13 + 1/16 +...
Rules:
You need to round the answer to 2 decimal places and return it as String.

If the given value is 0 then it should return 0.00

You will only be given Natural Numbers as arguments
### Solution
```Java
public class NthSeries {
 public static String seriesSum(int n) {
    if (n == 0){
      return "0.00";
    }
    double sum = 0;
    for (int i = 1; i <= n; i++){
      sum += (1. / (i * 3 - 2));
    }
    String result = String.format("%.2f",sum);
    return result;
 }
}        
```
### Favourite
```Java
import java.util.stream.IntStream;

public class NthSeries {
  
  public static String seriesSum(int n) {
    return String.format("%.2f",IntStream.iterate(1, e -> e + 3)
                .limit(n)
                .mapToDouble(x -> (1.0 / x))
                .sum());    
  }
}                     
```
[Task link](https://www.codewars.com/kata/555eded1ad94b00403000071)
### Task 2 (7kuy)
Cats and shelves                                                                                                                Description
An infinite number of shelves are arranged one above the other in a staggered fashion.
The cat can jump up to 3 shelves at the same time: from shelf 1 to shelf 2 or 4 (the cat cannot climb on the shelf directly above its head), according to the illustration. Find the minimum number of jumps to go from start to finish 
### Solution
```Java
public class Kata 
{
  public static int solution(int start, int finish)
  {
    return (finish - start) / 3 + (finish - start) % 3;
    }
}                    
```
### Favourite
```Java
public class Kata 
{
  public static int solution(int start, int finish) {
    int jump = 0;
    
    for(int i=0; i<finish; i++) {
      if(start+3 <= finish) {
        start+=3;
        jump++;
      } else if(start+2 < finish) {
        start+=2;
        jump++;
      } else if(start<finish){
        start++;
        jump++;
      }
    }
    return jump;
  }
}                  
```
[Task link](https://www.codewars.com/kata/62c93765cef6f10030dfa92b/java)
### Task 3 (7kuy)
Isograms          
An isogram is a word that has no repeating letters, consecutive or non-consecutive. Implement a function that determines whether a string that contains only letters is an isogram. Assume the empty string is an isogram. Ignore letter case.
### Solution
```Java
public class isogram {
    public static boolean  isIsogram(String str) {
      str = str.toLowerCase();
      char  str_1[] = str.toCharArray();
      for (int  i = 0; i < str.length(); i++) {
         for (int j = i + 1; j < str.length(); j++) {
             if (str_1[i] == str_1[j]) {
                 return false;
             }
          }
       }
      return true;
 }  
}                   
```
### Favourite
```Java
class isogram {
    public static boolean isIsogram(String str) {
        return str.toLowerCase()
                  .chars()
                  .distinct()
                  .count() == str.length();
    }
}                    
```
[Task link](https://www.codewars.com/kata/54ba84be607a92aa900000f1)