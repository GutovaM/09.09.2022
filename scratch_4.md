### Task 1 (6kuy)

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.
### Solution
```Java
public class FindOdd {
 public static int findIt(int[] a) {
   for (int i = 0; i < a.length; i++) {
            int count = 0;
            for (int j = 0; j < a.length; j++) {
                if (a[i] == a[j])
                    count++;
            }
            if (count % 2 != 0)
                return a[i];
        }
        return -1;
  }
}                            
```
### Favourite
```Java
import static java.util.Arrays.stream;

public class FindOdd {
  public static int findIt(int[] arr) {
    return stream(arr).reduce(0, (x, y) -> x ^ y);
  }
}                                                                
```
[Task link](https://www.codewars.com/kata/54da5a58ea159efa38000836)
### Task 2 (6kuy)

Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.
### Solution
```Java
class Persist {
 public static int persistence(long n) {
    int count = 0;
  while (n > 9){
      int p = 1;//произведение
      long k = n;
      while(k >= 1){
        p *= k % 10;
        k /= 10;
      }
      count += 1;
      n = p;
    }
    return count;
 }
} 
```
### Favourite
```Java
import java.util.Arrays;

class Persist {

    public static int persistence(long n) {
        if (n < 10) return 0;

        final long newN = Arrays.stream(String.valueOf(n).split(""))
                .mapToLong(Long::valueOf)
                .reduce(1, (acc, next) -> acc * next);

        return persistence(newN) + 1;
    }
}                      
```
[Task link](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec)
