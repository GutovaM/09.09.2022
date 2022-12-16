### Task 1 (6kuy)
Multiples of 3 or 5 

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).

Note: If the number is a multiple of both 3 and 5, only count it once.                              
### Solution
```java
public class Solution {

  public int solution(int number) {
    int result = 0;
    int i = 1;
    while(i < number){
      if(i % 3 == 0 || i % 5 == 0){
        result += i;
      }
      i++;
     }
     return result;
  }
}               
```
### Favourite
```java
import java.util.stream.IntStream;

public class Solution {
  public int solution(int number) {
    return IntStream.range(0, number)
                    .filter(n -> (n % 3 == 0) || (n % 5 == 0))
                    .sum();
  }
}
```
[Task link](https://www.codewars.com/kata/514b92a657cdc65150000006)
### Task 2 (6kuy)
Array.diff

Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

It should remove all values from list a, which are present in list b keeping their order.If a value is present in b, all of its occurrences must be removed from the other. 
### Solution
```java
public class Kata {

  public static int[] arrayDiff(int[] a, int[] b) {
    int[] a_1;
    for (int j = 0 ; j<b.length; j++){
      for (int i = 0 ; i < a.length ; i++){
        if ( a[i] == b[j]){
          a_1 = new int[a.length-1];
           for ( int t = 0; t < a.length; t++){
             if( t < i ){
               a_1[t] = a[t];
             }
             if(t>i){
               a_1[t-1] = a[t];
             }
           }
          a = a_1;
          i--;
        }
      }
    }
    return a;
  }
}  
```
### Favourite
```java
import org.apache.commons.lang3.ArrayUtils;
import java.util.Arrays;

public class Kata {

  public static int[] arrayDiff(int[] a, int[] b) {
    
    for (int i = 0; i < b.length; i++)
      a = ArrayUtils.removeAllOccurences(a, b[i]);
    return a;
  }

}
```
[Task link](https://www.codewars.com/kata/523f5d21c841566fde000009)