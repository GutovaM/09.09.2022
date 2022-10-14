### Task 1 (6kuy)

Count the smiley faces!

Given an array (arr) as an argument complete the function countSmileys that should return the total number of smiling faces.

Rules for a smiling face:

Each smiley face must contain a valid pair of eyes. Eyes can be marked as : or ;
A smiley face can have a nose but it does not have to. Valid characters for a nose are - or ~
Every smiling face must have a smiling mouth that should be marked with either ) or D
No additional characters are allowed except for those mentioned.
### Solution
```Java
import java.util.*;

public class SmileFaces {

    public static int countSmileys(List<String> arr) {
        if (arr.size() == 0){
            return 0;
        }
        int count = 0;
        int i = 0;
        while(i < arr.size()){
            if(arr.get(i).length() == 2 &&
                    (arr.get(i).charAt(0) == ':' || arr.get(i).charAt(0) == ';') && 
                    (arr.get(i).charAt(1) == ')' || arr.get(i).charAt(1) == 'D')){
                count += 1;
            }
            if(arr.get(i).length() == 3 &&
                    (arr.get(i).charAt(0) == ':' || arr.get(i).charAt(0) == ';') &&
                    (arr.get(i).charAt(1) == '-' || arr.get(i).charAt(1) == '~') &&
                    (arr.get(i).charAt(2) == ')' || arr.get(i).charAt(2) == 'D')){
                count += 1;
            }
            i++;
        }
        return count;
    }
}                    
```
### Favourite
```Java
import java.util.*;

public class SmileFaces {

    public static int countSmileys(List<String> arr) {
        return (int)arr.stream().filter( x -> x.matches("[:;][-~]?[)D]"))
                .count();
    }
}                                                                     
```
[Task link](https://www.codewars.com/kata/583203e6eb35d7980400002a/java)
### Task 2 (6kuy)
Find the missing letter

Write a method that takes an array of consecutive (increasing) letters as input and that returns the missing letter in the array.

You will always get an valid array. And it will be always exactly one letter be missing. The length of the array will always be at least 2.
The array will always contain letters in only one case.
### Solution
```Java
public class Kata
{
    public static char findMissingLetter(char[] array)
    {
        int i = 1;
        while(i < array.length){
            if(array[i]-array[i-1] != 1){
                return (char)(array[i]-1);
            }
            i++;
        }
        return ' ';
    }
}               
```
### Favourite
```Java
public class Kata
{
    public static char findMissingLetter(char[] array) {
        int n = 0;
        while ( 1 + (int) array[n] == (int) array[++n] ) {}
        return ++array[--n];
    }
}                      
```
[Task link](https://www.codewars.com/kata/5839edaa6754d6fec10000a2)
