### Task 1 (7kuy)
Complementary DNA                    
Your task is to write a function which returns the sum of following series upto nth term(parameter).
Deoxyribonucleic acid (DNA) is a chemical found in the nucleus of cells and carries the "instructions" for the development and functioning of living organisms.

If you want to know more: http://en.wikipedia.org/wiki/DNA

In DNA strings, symbols "A" and "T" are complements of each other, as "C" and "G". Your function receives one side of the DNA (string, except for Haskell); you need to return the other complementary side. DNA strand is never empty or there is no DNA at all (again, except for Haskell).

More similar exercise are found here: http://rosalind.info/problems/list-view/ (source)
### Solution
```Java
public class DnaStrand {
    public static String makeComplement(String dna) {
        String dna_1 = "";
        int i = 0;
        while(i < dna.length()){
            if(dna.charAt(i) == 'A'){
                dna_1 += "T";
            }
            if(dna.charAt(i) == 'T'){
                dna_1 += "A";
            }
            if(dna.charAt(i) == 'G'){
                dna_1 += "C";
            }
            if(dna.charAt(i) == 'C'){
                dna_1 += "G";
            }
            i++;
        }
        return dna_1;
    }
}       
```
### Favourite
```Java
public class DnaStrand {
    public static String makeComplement(String dna) {
        return dna.replace("A","B")
                .replace("C","D")
                .replace("T","A")
                .replace("G","C")
                .replace("B","T")
                .replace("D","G");
    }
}                                                   
```
[Task link](https://www.codewars.com/kata/554e4a2f232cdd87d9000038/java)
### Task 2 (7kuy)
Sorted? yes? no? how?

Complete the method which accepts an array of integers, and returns one of the following:

"yes, ascending" - if the numbers in the array are sorted in an ascending order
"yes, descending" - if the numbers in the array are sorted in a descending order
"no" - otherwise
You can assume the array will always be valid, and there will always be one correct answer.
### Solution
```Java
class Solution {

    public static String isSortedAndHow(int[] array) {

        boolean descending = false;
        boolean ascending = false;
        int i = 1;
        while(i < array.length){
            if(array[i] > array[i-1]){
                ascending = true;
            }
            if(array[i] < array[i-1]){
                descending = true;
            }
            i++;
        }
        if(ascending && !descending){
            return "yes, ascending";
        }
        if(descending && !ascending){
            return "yes, descending";
        }
        return "no";
    }
} 
```
### Favourite
```Java
import java.util.stream.IntStream;

class Solution {

    public static String isSortedAndHow(int[] array) {
        if(IntStream.range(0, array.length-1).allMatch(i -> array[i] <= array[i+1]))
            return "yes, ascending";

        if(IntStream.range(0, array.length-1).allMatch(i -> array[i] >= array[i+1]))
            return "yes, descending";

        return "no";
    }
}                          
```
[Task link](https://www.codewars.com/kata/580a4734d6df748060000045)
