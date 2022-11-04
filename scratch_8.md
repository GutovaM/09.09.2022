### Task 1 (6kuy)
Create Phone Number

Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number. 
### Solution
```Java
public class Kata {
  public static String createPhoneNumber(int[] numbers) {
    return "(" + numbers[0] + numbers[1] + numbers[2] + ") " + numbers[3] + 
      numbers[4] + numbers[5] + "-" + numbers[6] + numbers[7] + numbers[8] + numbers[9];
  }
}          
```
### Favourite
```Java
public class Kata {
    public static String createPhoneNumber(int[] numbers) {
        String phoneNumber = new String("(xxx) xxx-xxxx");

        for (int i : numbers) {
            phoneNumber = phoneNumber.replaceFirst("x", Integer.toString(i));
        }

        return phoneNumber;
    }
}   
```
[Task link](https://www.codewars.com/kata/525f50e3b73515a6db000b83/solutions/java)
### Task 2 (6kuy)
Sum of Digits / Digital Root

Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.
### Solution
```Java
public class DRoot {
    public static int digital_root(int n) {
        while(n / 10 != 0){
            n = n / 10 + n % 10;
        }
        return n;
    }
}       
```
### Favourite
```Java
public class DRoot {
    public static int digital_root(int n) {
        return (n != 0 && n%9 == 0) ? 9 : n % 9;
    }
} 
```
[Task link](https://www.codewars.com/kata/541c8630095125aba6000c00/solutions/java)
