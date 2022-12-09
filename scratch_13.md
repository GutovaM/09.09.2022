### Task 1 (6kuy)
Find Numbers with Same Amount of Divisors

The integers 14 and 15, are contiguous (1 the difference between them, obvious) and have the same number of divisors.Let's name, diff, the difference between two integers, next and prev, (diff = next - prev) and nMax, an upper bound of the range.

We need a special function, count_pairsInt(), that receives two arguments, diff and nMax and outputs the amount of pairs of integers that fulfill this property, all of them being smaller (not smaller or equal) than nMax.

Let's see it more clearly with examples.   
### Solution
```java
public class SameNbDivisors {
    public static int countPairsInt(int diff, long nMax) {
      int result = 0;
      int i = 1;
      while(i + diff < nMax){
        int x = 0;
        int y = 0;
        for(int j = 1; j <= i + diff; j++){
          if (i % j == 0) {
            x++;
          }
          if ((i + diff) % j == 0){
            y++;
          }
        }
        if (x == y){
          result++;
        }
        i++;
      }
      return result;
    }
}     
```
### Favourite
```java
public class SameNbDivisors {   
    public static int countPairsInt(int diff, long nMax) {
        int count = 0;
        for(int i = 2;i<nMax-diff;i++){          
           if(divisors(i)==divisors(i+diff)){count++;}    
        }
        return count;
    }
    public static int divisors(int n) {
        int count=2;
        for (int j = 2; j <= n / 2; j++) {
            if (n % j == 0) {count++;}
        }
        return count;
    }
}
```
[Task link](https://www.codewars.com/kata/55f1614853ddee8bd4000014)
### Task 2 (6kuy)
Handshake problem  

Johnny is a farmer and he annually holds a beet farmers convention "Drop the beet".

Every year he takes photos of farmers handshaking. Johnny knows that no two farmers handshake more than once. He also knows that some of the possible handshake combinations may not happen.

However, Johnny would like to know the minimal amount of people that participated this year just by counting all the handshakes.

Help Johnny by writing a function, that takes the amount of handshakes and returns the minimal amount of people needed to perform these handshakes (a pair of farmers handshake only once).
### Solution
```java
public class Kata
{
  public static int GetParticipants(int handshakes)
  {
    int i = 0;
    int result = 0;
    while(true){
      result = i + 1;
      if(result * i > handshakes * 2){
       break;
      }
      if(result * i == handshakes * 2){
        break;
      } 
      result++;
      i++;
    }
    if(result == 1){
      result = 0;
    }
    return result;
  }
}  
```
### Favourite
```java
public class Kata
{
  public static int GetParticipants(int n)
  { 
    int i = 0;
      
      while(i*(i-1)/2 < n){ i++; }
    
    return i;
  }
}
```
[Task link](https://www.codewars.com/kata/5574835e3e404a0bed00001b)
