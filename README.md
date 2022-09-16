# 09.09.2022
### Task 1 (8kuy)
N-th Power                                                                                                                              

You are given an array with positive numbers and a non-negative number N. You should find the N-th power of the element in the array with the index N. If N is outside of the array, then return -1. Don't forget that the first element has the index 0.

Let's look at a few examples:

array = [1, 2, 3, 4] and N = 2, then the result is 3^2 == 9;
array = [1, 2, 3] and N = 3, but N is outside of the array, so the result is -1.    
### Solution
```Java
public class Kata {
  public static int nthPower(int[] array, int n) {
    int result;
    if (array.length > n){
      result = (int) Math.pow (array[n], n);
    }
    else{
      result = -1;
    }
    return result;
  }
}
```
### Favourite
```Java
public class Kata {
  public static int nthPower(int[] array, int n) {
    return n < array.length ? (int) Math.pow(array[n], n) : -1;
  }
}
```
[Task link](https://www.codewars.com/kata/57d814e4950d8489720008db/java)

### Task 2 (8kuy)
Basic Mathematical Operations  

Your task is to create a function that does four basic mathematical operations.

The function should take three arguments - operation(string/char), value1(number), value2(number).
The function should return result of numbers after applying the chosen operation.        
### Solution
```Java
public class BasicOperations
{
  public static Integer basicMath(String op, int v1, int v2)
  {
    var v3 = 0;
    if (op == "+"){
      v3 = v1 + v2;
    }  
    if (op == "-") {
      v3 = v1 - v2;
    } 
    if (op == "*") {
      v3 = v1 * v2;
    } 
    if (op == "/") {
      v3 = v1 / v2;
    }
    return v3;
  }
}
```
### Favourite
```Java
public class BasicOperations
{
  public static Integer basicMath(String op, int v1, int v2)
  {
    return switch(op) {
                case "+" -> v1+v2;
                case "-" -> v1-v2;
                case "*" -> v1*v2;
                case "/" -> v1/v2;
                default -> null;
            };
  }
}
```
[Task link](https://www.codewars.com/kata/57356c55867b9b7a60000bd7)

### Task 3 (8kuy)
To square(root) or not to square(root) 

Write a method, that will get an integer array as parameter and will process every number from this array.
Return a new array with processing every number of the input-array like this:
If the number has an integer square root, take this, otherwise square the number.

Example
[4,3,9,7,2,1] -> [2,9,3,49,4,1]
Notes
The input array will always contain only positive numbers, and will never be empty or null.       
### Solution
```Java
public class Kata
{
  public static int[] squareOrSquareRoot(int[] array)
  {
    int[] array_1 = new int[array.length]; 
    for (int i = 0; i < array.length; i++){
      if (Math.sqrt(array[i]) % 1 == 0){
        array_1[i] = (int) Math.sqrt (array[i]);
      }
      else{
        array_1[i] = (int) Math.pow (array[i], 2);
      }                       
    }
    return array_1;
  }
}
```
### Favourite
```Java
public class Kata {
    public static int[] squareOrSquareRoot(int[] array) {
        return java.util.stream.IntStream.of(array).map
                (x -> (int) (Math.sqrt(x) == (int) Math.sqrt(x) ? 
                        Math.sqrt(x) : Math.pow(x, 2))).toArray();
    }
}
```
[Task link](https://www.codewars.com/kata/57f6ad55cca6e045d2000627)
