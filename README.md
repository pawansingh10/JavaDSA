# JavaDSA

## DSA by Java Repository 









































































































































## Recursion
* Recursion is build up of concept of function
* A function calling itself is called Recursion

### Why need of Recursion?
- To Break Complex Problem into Smaller Sub-problems 
- Because we know the solution or easily solve the smaller sub-problem
- At last sum of all smaller sub-problem solution gives the solution of complex problems
- ***DIVIDE AND CONQUER***

### 3 Parts of Recursion
1. **Base Case**
2. **Find the Relation between Complex problem and Smaller Subproblem**
3. **Generalize the Solution**

### Code
```java
//Factorial of a num using Recursion
int fact(int n)
{
  if(n==0)
  {
   return 1;
  }
  return n*fact(n-1); 
}
```

```Java
   //nth Fibonnacci term
   int fib(int n){
   if(n==1) return 0;
   if(n==2) return 1;
   else return fib(n-1)+fib(n-2);
```
