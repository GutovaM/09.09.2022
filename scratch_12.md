### Task 1 (6kuy)
The Supermarket Queue 

There is a queue for the self-checkout tills at the supermarket. Your task is write a function to calculate the total time required for all the customers to check out!

input
customers: an array of positive integers representing the queue. Each integer represents a customer, and its value is the amount of time they require to check out.
n: a positive integer, the number of checkout tills. 
### Solution
```java
import java.util.Arrays;
public class Solution {

    public static int solveSuperMarketQueue(int[] customers, int n) {
      if(customers.length == 1)
      {
        return customers[0];
      }
      if(customers.length == 0)
      {
        return 0;
      }
      if(n >= customers.length)
      {
        int m = customers[0];
        for (int i = 0; i < customers.length; i++){
         if (customers[i] > m){
           m = customers[i];
         }
       }
        return m;
      }
      int a[] = new int[n];
      for(int i = 0; i < n; ++i)
      {
        a[i] = customers[i];
      }
      
      int d = n;
      
      while(d < customers.length){
            int minIndex = 0;
            for(int i = 0; i < n; ++i)
            {
              if(a[i] < a[minIndex])
              {
                minIndex = i;
              }
            }
            a[minIndex] += customers[d];
            ++d;
      }
     int max = a[0];
     for (int i = 0; i < a.length; i++) 
     {
        if (a[i] > max) 
        {
          max = a[i];
        }
     }
     return max;
  }  
}    
```
### Favourite
```java
import java.util.Arrays;
public class Solution {

    public static int solveSuperMarketQueue(int[] customers, int n) {
      int[] result = new int[n];
      for(int i = 0; i < customers.length; i++){
        result[0] += customers[i];
        Arrays.sort(result);
      }
      return result[n-1];
    }
    
}
```
[Task link](https://www.codewars.com/kata/57b06f90e298a7b53d000a86)
### Task 2 (6kuy)
Who won the election? 

In democracy we have a lot of elections. For example, we have to vote for a class representative in school, for a new parliament or a new government.

Usually, we vote for a candidate, i.e. a set of eligible candidates is given. This is done by casting a ballot into a ballot-box. After that, it must be counted how many ballots (= votes) a candidate got.

A candidate will win this election if he has the absolute majority.

Your Task
Return the name of the winner. If there is no winner, return null / nil / None depending on the language.

Task Description
There are no given candidates. An elector can vote for anyone. Each ballot contains only one name and represents one vote for this name. A name is an arbitrary string, e.g. "A", "B", or "XJDHD". There are no spoiled ballots.

The ballot-box is represented by an unsorted list of names. Each entry in the list corresponds to one vote for this name. You do not know the names in advance (because there are no candidates).

A name wins the election if it gets more than n / 2 votes (n = number of all votes, i.e. the size of the given list).
### Solution
```java
import java.util.List;

public class BallotsCounter {

    public static String getWinner(final List<String> listOfBallots) {
      int n = listOfBallots.size();
      int k = listOfBallots.size()/2;
      String result = null;
      int[] counter = new int[n];
      for (int i = 0; i < n; i++) {
        String p = listOfBallots.get(i);
        int count = ++counter[p.hashCode() % n];
        if (count > k) {
          k = count;
          result = p;
        }
      }
      return result;
    }
}                               
```
### Favourite
```java
import java.util.List;
import java.util.HashSet;
import java.util.Collections;

public class BallotsCounter {

    public static String getWinner(final List<String> listOfBallots) {
      HashSet<String> unique = new HashSet<String>(listOfBallots);
      for (String n : unique) {
        if (Collections.frequency(listOfBallots, n) > listOfBallots.size()/2) return n;
      }
      return null;
    }

}
```
[Task link](https://www.codewars.com/kata/554910d77a3582bbe300009c)