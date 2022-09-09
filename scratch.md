### Task 1 (8kuy)
You will be given an array a and a value x. All you need to do is check whether the provided array contains the value.

Array can contain numbers or strings. X can be either.

Return true if the array contains the value, false if not.

### Solution
```Java
public class Solution {

    public static boolean check(Object[] arr, Object value) {
        for (int i = 0; i < arr.length; i++){
          if (arr[i] == value) return true;
     }
        return false;
    }

}
```
### Favourite
```Java
import java.util.Arrays;

public class Solution
{

    public static boolean check(Object[] a, Object x)
    {
        return Arrays.stream( a )
                .anyMatch( e -> e == x );
    }

}
```
### Task 2 (8kuy)
You are given the length and width of a 4-sided polygon. The polygon can either be a rectangle or a square.
If it is a square, return its area. If it is a rectangle, return its perimeter.

Example(Input1, Input2 --> Output):

6, 10 --> 32
3, 3 --> 9
Note: for the purposes of this kata you will assume that it is a square if its length and width are equal, otherwise it is a rectangle.
### Solution
```Java
public class Solution {
    public static int areaOrPerimeter (int l, int w) {
        if (l == w){
          return l * w;
        }
      else{
        return 2 * (l + w);
      }
    }
}
```
### Favourite
```Java
public class Solution {
    public static int areaOrPerimeter (int l, int w) {
        return l == w ? l * w : (l + w) * 2;
    }
}
```
