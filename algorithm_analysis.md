 - asymptotic analysis is used to measure the order of growth
 - it's machine, language, etc. independent
 - we can analyse pseudo code or algorithm before implementing it
 - order of growth(general trend) is dependent on largest number of operation in a program

 ### counting number of operations
 consider a problem where you need to add `n` natural numbers
 ```
 int addNaturalNumbers(int n) {
    return n*(n+1)/2;
 }
 // operation: c1 + c2 + c3 or c4
 // takes constant time
 // order of growth: constant (c4 or take any constant)
 ```

 ```
int addNaturalNumbers(int n) {
    int sum=0;
    for(int i=0; i<=n; i++) {
      sum++;
    }
    return sum;
}
// operation: c2*n + c1 + c3 or c2*n + c4
// takes linear time
// order of growth: linerar (n)
 ```

order of growth is the general trend, so if we have all operation taking constant time(`1st code`) the order of growth will be `constant`, if we have biggest no. of constant operation depending on n(`2nd code`), we have `linear` order of growth, as the n grows the more time in will take

---
consider the following code:
```
int placeBet(int n) {
    if(n%2 != 0) {
      return 0;
    }
    int total=0;
    for(int i=0; i<=n; i++) {
      total++;
    }
    return total;
}
```
the above code (although extremly biased for bets) will have constant order of growth if placed bet is odd and linear order of growth if placed bet is even, in such case we can consider 3 cases

considering placeBet() code, assuming placeBet() is called 100 times
## Best Case(rarely useful)
- assume all the places bets are odd
- order of growth: constant
## Average Case(usually impractical)
- assume 50% placed bets are odd and 50% placed bets are even
- order of growth: linear
## Worst Case(most helpful and usually used)
- all the places bets are even
- order of growth: linear

# Order of growth
#### mathematically f(n) is said to growing faster than g(n) if following conditions are true, where f(n) and g(n) are time taken by the algorithm and n>=0, f(n),g(n) >=0:
- Limit(n->infinity) g(n)/f(n) = 0
- Limit(n->infinity) f(n)/g(n) = infinity

#### direct way to determine order of growth and compare them:
- ignore lower order terms
- ignore constant of leading term

for comparision follow the following presidence:
c < log log n < log n < n^(1/3) < n^(1/2) < n < n^2 < n^3 < n^4 < 2^n < n^n

for example:\
f(n): 3n^2 + 2n + 5 = n^2(quadratic)\
g(n): 2n + 4 = n(linear)\
h(n): 8 = c(constant)

as n^2 is greater that c or n, therefore f(n) order of growth is highest and h(n) is lowest

if you compare these order of growths:\
f(n): n^2\
g(n): n log n\
you can divide both order of growth by n which will lead:\
f(n): n\
g(n): log n\
now we can clearly see that f(n) order of growth > g(n) order of growth