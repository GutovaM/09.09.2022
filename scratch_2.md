### Task 1 (7kuy)
Task

Below we will define what and n-interesting polygon is and your task is to find its area for a given n.

A 1-interesting polygon is just a square with a side of length 1. An n-interesting polygon is obtained by taking the n - 1-interesting polygon and appending 1-interesting polygons to its rim side by side. You can see the 1-, 2- and 3-interesting polygons in the picture below.

Example
For n = 1, the output should be 1;

For n = 2, the output should be 5;

For n = 3, the output should be 13.
### Solution
```Java
public class Kata {
    public static int shapeArea(int n) {
      return n * ((n - 1) * 2) + 1;
    }
}
```
### Favourite
```Java
public class Kata {
    public static int shapeArea(int n) {
    int result = 2 * n - 1;
    for (int i = n - 1; i >= 1; i--) {
      result += 2 * (2 * i - 1);
    }
    return result;
  }
}
```
[Task link](https://www.codewars.com/kata/5893e0c41a88085c330000a0/java)
### Task 2 (7kuy)
Sum of odd numbers

Given the triangle of consecutive odd numbers.
Calculate the sum of the numbers in the nth row of this triangle (starting at index 1) e.g.

### Solution
```Java
class RowSumOddNumbers {
    public static int rowSumOddNumbers(int n) {
        if ( n == 1 ){
            return 1;
        }
        int i = (n * n ) - (n - 1);
        int result = 0;
        for (int j = 1; j <= n ; j ++){
            result += i;
            i += 2;
        }
        return result;
    }
}
```
### Favourite
```Java
class RowSumOddNumbers {
    public static int rowSumOddNumbers(int n) {
        return n * n * n;
    }
}
```
[Task link](https://www.codewars.com/kata/55fd2d567d94ac3bc9000064/java)
### Task 3 (7kuy)
Breaking chocolate problem

Your task is to split the chocolate bar of given dimension n x m into small squares. Each square is of size 1x1 and unbreakable. Implement a function that will return minimum number of breaks needed.

For example if you are given a chocolate bar of size 2 x 1 you can split it to single squares in just one break, but for size 3 x 1 you must do two breaks.

If input data is invalid you should return 0 (as in no breaks are needed if we do not have any chocolate to split). Input will always be a non-negative integer.
### Solution
```Java
public class Chocolate{
  public static int breakChocolate(int n, int m) {
    if (n <= 0 || m <= 0)
    {
      return 0;
    }
    return (n * m) - 1;
  }
}
```
### Favourite
```Java
public class Chocolate{
  public static int breakChocolate(int n, int m) {
    if (n==0 || m==0) return 0;
    
    return (Math.min(n, m) - 1 + (Math.min(n,m)*(Math.max(n,m)-1)));
  }
}
```
[Task link](https://www.codewars.com/kata/534ea96ebb17181947000ada)