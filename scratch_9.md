### Task 1 (6kuy)
Delete occurrences of an element if it occurs more than n times

Alice and Bob were on a holiday. Both of them took many pictures of the places they've been, and now they want to show Charlie their entire collection. However, Charlie doesn't like these sessions, since the motif usually repeats. He isn't fond of seeing the Eiffel tower 40 times.
He tells them that he will only sit for the session if they show the same motif at most N times. Luckily, Alice and Bob are able to encode the motif as a number. Can you help them to remove numbers such that their list contains each number only up to N times, without changing the order?
### Solution
```Java
import java.util.ArrayList;
import java.util.List;
import java.util.Arrays;

public class EnoughIsEnough {

    public static int[] deleteNth(int[] elements, int maxOccurrences) {
        List<Integer> elements_1 = new ArrayList<Integer>();
        int count = 0;
        for (int i = 0; i < elements.length; i++) {
            count = 0;
            for (int j = 0; j <= i; j++) {
                if (elements[j] == elements[i]){
                    count += 1;
                }
            }
            if (count <= maxOccurrences){
                elements_1.add(elements[i]);
            }
        }
        int[] elements_2 = new int[elements_1.size()];
        for (int i = 0; i < elements_1.size(); i++){
            elements_2[i] = elements_1.get(i);
        }
        return elements_2;

    }
}           
```
### Favourite
```Java
import java.util.HashMap;
import java.util.Map;
import java.util.stream.IntStream;

public class EnoughIsEnough {
    public static int[] deleteNth(int[] elements, int maxOccurrences) {
        Map<Integer, Integer> occurrence = new HashMap<>();
        return IntStream.of(elements)
                .filter(motif -> occurrence.merge(motif, 1, Integer::sum) <= maxOccurrences)
                .toArray();
    }
}    
```
[Task link](https://www.codewars.com/kata/554ca54ffa7d91b236000023)
### Task 2 (6kuy)
Roman Numerals Encoder

Create a function taking a positive integer as its parameter and returning a string containing the Roman Numeral representation of that integer.

Modern Roman numerals are written by expressing each digit separately starting with the left most digit and skipping any digit with a value of zero. In Roman numerals 1990 is rendered: 1000=M, 900=CM, 90=XC; resulting in MCMXC. 2008 is written as 2000=MM, 8=VIII; or MMVIII. 1666 uses each Roman symbol in descending order: MDCLXVI.
### Solution
```Java
public class Conversion {

    public String solution(int n) {
        String[] n_4 = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
        String[] n_3 = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        String[] n_2 = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        String[] n_1 = {"", "M", "MM", "MMM"};
        return n_1[n/1000] + n_2[n%1000/100] + n_3[n%100/10] + n_4[n%10];
    }
}           
```
### Favourite
```Java
import java.util.*;

public class Conversion {

    private static TreeMap<Integer, String> MAP;
    static {
        MAP = new TreeMap<Integer, String>(Collections.reverseOrder());
        MAP.put( 1, "I" );
        MAP.put( 4, "IV" );
        MAP.put( 5, "V" );
        MAP.put( 9, "IX" );
        MAP.put( 10, "X" );
        MAP.put( 40, "XL" );
        MAP.put( 50, "L" );
        MAP.put( 90, "XC" );
        MAP.put( 100, "C" );
        MAP.put( 400, "CD" );
        MAP.put( 500, "D" );
        MAP.put( 900, "CM" );
        MAP.put( 1000, "M" );
    }

    public String solution(int n) {
        StringBuilder builder = new StringBuilder();
        for( Map.Entry<Integer, String> entry: MAP.entrySet() ){
            int i = entry.getKey();
            String s = entry.getValue();
            while( n>=i ){
                builder.append(s);
                n -= i;
            }
        }
        return builder.toString();
    }
}  
```
[Task link](https://www.codewars.com/kata/51b62bf6a9c58071c600001b)
