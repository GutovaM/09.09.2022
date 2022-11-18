### Task 1 (6kuy)
Return 1, 2, 3 randomly

You have function one_two (oneTwo for Java) that returns 1 or 2 with 50% chance. one_two is already defined in a global scope and can be called everywhere.

Your goal is to create function one_two_three (oneTwoThree for Java) that returns 1, 2 or 3 with equal probability using only one_two function.

Do not try to cheat returning repeating non-random sequences. There is randomness test especially for this case.
### Solution
```Java
import static preload.Preload.oneTwo;

public class Main {

    public static int oneTwoThree() {
        int x = oneTwo() + 10 * oneTwo();
        if(x == 11){
            return 1;
        }
        if(x == 12){
            return 2;
        }
        if(x == 22){
            return 3;
        }
        return oneTwoThree();
    }
}  
```
### Favourite
```Java
import static preload.Preload.oneTwo;

public class Main {

    public static int oneTwoThree() {
        return oneTwo() == 1 ? (oneTwo() == 1 ? 1 : 2) : (oneTwo() == 1 ? 3 : oneTwoThree());
    }
} 
```
[Task link](https://www.codewars.com/kata/593e84f16e836ca9a9000054)
### Task 2 (6kuy)
Persistent Bugger

Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.                                                                                                                                                                                                  class Persist {

### Solution
```Java
class Persist {
    public static int persistence(long n) {
        int i = 0;
        while(n >= 10) {
            int m = 1;
            while (n > 0) {
                m *= (n % 10);
                n /= 10;
            }
            n = m;
            i++;
        }
        return i;
    }
}                  
```
### Favourite
```Java
class Persist {
    public static int persistence(long n) {
        int times = 0;
        while (n >= 10) {
            n = Long.toString(n).chars().reduce(1, (r, i) -> r * (i - '0'));
            times++;
        }
        return times;
    }
}            
```
[Task link](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec)
