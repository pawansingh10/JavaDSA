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
   }
```

```Java
// Given a num n, find the minimum steps to minimize the num n to 1
// If n is divisible by 3, n->n/3
// If n is divisible by 3, n->n/2
// Decrement the num by 1, n->n-1
   
   int count=0;
   while(n>1){
       if(n%3==0) n=n/3;
       if(n%2==0) n=n/3;
       else n=n-1;
       count++;
   }
//This seems to be logically correct but actually it is not like in case of 10
   
   
//So actual correct logic
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int temp=n;
		int count=0;
		while(n>1){
		    if(n%3==0){
		        n/=3;
		    }
		    else if(n%2==0){
		        n/=2;
		    }
		    else{
		        n--;
		    }
		    count++;
		}
		n=temp;
		int count1=0;
		while(n>1){
		    if(n%2==0){
		        n/=2;
		    }
		    else if(n%3==0){
		        n/=3;
		    }
		    else{
		        n--;
		    }
		    count1++;
		}
		n=temp;
		int count2=0;
		while(n>1){
		    if(n%2!=0 && n%3!=0){
		        n--;
		    }
		    if(n%2==0){
		        n/=2;
		    }
		    else if(n%3==0){
		        n/=3;
		    }
		    count2++;
		}
		System.out.println(count+" "+ count1+" "+count2);
		System.out.println(Math.min(count,Math.min(count1,count2)));
	}
}

```

```Java
//min steps to reduce n to 1 through recursion
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		System.out.println(minSteps(n));
	}
	public static int minSteps(int n){
	    if(n==1){
	        return 0;
	    }
	   
	    int sub = Integer.MAX_VALUE; // min step to reduce n to n-1
	    int div3 = Integer.MAX_VALUE;
	    int div2 = Integer.MAX_VALUE;
	    sub = minSteps(n-1);
	    if(n%3==0){
	        div3=minSteps(n/3);
	    }
	    if(n%2==0){
	        div2=minSteps(n/2);
	    }
	    return  1+Math.min(sub,Math.min(div3,div2));
	}
}
```
