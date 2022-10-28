### Task 1 (6kuy)
Who likes it?

You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples: []                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
### Solution
```Java
class Solution {
    public static String whoLikesIt(String... names) {
      String result = "";
      if(names.length == 0){
          result = "no one likes this";
      }
      if(names.length == 1){
        result = names[0] + " likes this";
      }
      if(names.length == 2){
        result = names[0] + " and " + names[1] + " like this";
      }
      if(names.length == 3){
        result = names[0] + ", " + names[1] + " and " + names[2] + " like this";
      }
      if(names.length > 3){
        int other = names.length - 2;
        result = names[0] + ", " + names[1] + " and " + other + " others like this";
      }
      return result;
    }
}
```
### Favourite
```Java
class Solution {
    public static String whoLikesIt(String... nms) {
        switch (nms.length) {
          case 0: return "no one likes this";
          case 1: return String.format("%s likes this", nms[0]);
          case 2: return String.format("%s and %s like this", nms[0], nms[1]);
          case 3: return String.format("%s, %s and %s like this", nms[0], nms[1], nms[2]);
          default: return String.format("%s, %s and %d others like this", nms[0], nms[1], nms.length - 2);
        }
    }
} 
```
[Task link](https://www.codewars.com/kata/5266876b8f4bf2da9b000362)

### Task 2 (6kuy)
Convert string to camel case

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).
### Solution
```Java
import java.lang.StringBuilder;
class Solution{

  static String toCamelCase(String s){
    String result = "";
    char[] s_1 =  s.toCharArray();
    for(int i = 0; i < s_1.length; i++) {
      if(s_1[i] == '-' || s_1[i] == '_') {
        result += Character.toUpperCase(s_1[i + 1]);
        i++;
      } else {
        result += s_1[i];
      }
    }
    return result;
  }
}   
```
### Favourite
```Java
import java.lang.StringBuilder;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Solution{

  static String toCamelCase(String s){
    return Pattern.compile("[-|_](.)").matcher(s).replaceAll(r -> r.group(1).toUpperCase());
  }
}                                                
```
[Task link](https://www.codewars.com/kata/517abf86da9663f1d2000003/java)