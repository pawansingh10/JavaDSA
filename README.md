# JavaDSA

## DSA by Java Repository 

- ***Success is Vector(Magnitude+Direction)***

### Computer Programming == Computer + Program

### DSA == Data Structure + Algorithm


### Print Hello
```Code
public class Main
{
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```

### Variable,Memory
- Variable declaration
- Variable Initialization
- variable Assignment


### Data Types

#### Primitive Data types
1. int       ->  4 bytes
2. long      ->  8 bytes
3. float     ->  4 bytes
4. double    ->  8 bytes
5. char      ->  2 bytes
6. short     ->  2 bytes
7. byte      -> 1 byte
8. boolean   -> 1 byte

#### Non-Primitive Data types
1. String
2. Array


### Packages
- Collection of pre-written code by developers
- Scanner -> import java.util.scanner;
- System  -> import java.lang.*;
- Math    -> import java.util.math;



### Taking input
```code
     Scanner sc = new Scanner(System.in);
     
     int a = sc.nextInt();
     int b = sc.nextLong();
     int c = sc.nextFloat();
     int d = sc.nextDouble();
     int e = sc.nextShort();
     int f = sc.nextBoolean();
     int g = sc.nextByte();
     char h = sc.nextChar();
     
     String s = sc.next();
     String str = sc.nextLine();
     
```

### Operators
```code
   int c=a+b;
   int c=a-b;
   int c=a*b;
   int c=a/b;
   int c=a%b;
   
   if(a<b)
   else if(a>b)
   else if(a<=b)
   else if(a>=b)
   
   if(a==b && b==c)
   if(a==b || b==c)
   if(a!=b)
```

### Loops
```Code
   //For loop
   for(int counter=1; counter<=10; count++)
   {
     System.out.println("Counter:"+counter);
   }
   
   //While loop
   int i=1;
   while(i<10)
   {
     System.out.println("Hello:"+i);
     i++;
   }
   
   // do while loop
   int i=0;
   do{
      System.out.println("Hello"+i);
      i++;
   }while(i<10);
```


### Type Casting
- UpCastiing -> Automatically
-```int to double ```
- DownCasting -> Manually 
-```double to int```


### Pattern Printing





### ARRAYS
- Contiguous Memory Allocation that is used to store similar data type 
- ```code
     int [] arr = new int[10];
     //Taking array input
     for(int i=0; i<10; i++){
         arr[i]=sc.nextInt();
     }
     //Printing array element
     for(int i=0; i<10; i++){
         System.out.print(arr[i]+" ");
     }```

### 2D ARRAYS
- Array of Arrays
- Excelsheet, ChessBoard, ClassRoom
- ```code
  //Sum of black and white in chesscard
  
```
```code
  //Zig-Zag Trversal of Array
```



### Switch 
```code
import java.util.*;
public class Main
{
  public static void main (String[]args)
  {
    int num = 8;
    switch (num)
      {
      case 1:
	System.out.println ("MON");
	break;
	case 2:System.out.println ("TUE");
	break;
	case 3:System.out.println ("WED");
	break;
	case 4:System.out.println ("THU");
	break;
	case 5:System.out.println ("FRI");
	break;
	case 6:System.out.println ("SAT");
	break;
	case 7:System.out.println ("SUN");
	break;
	default:System.out.println ("Wrong Input");
      }

  }
}

```


### CHARACTER
- Special character to store every thing
- Capital Letter, Small Letter, Numbers, Symbols
- Computer only understand only 0/1, then how we these values store
- They are store using **ASCII** Universal Standards followed by compiler to use the character
- ASCII from =='A' to 'Z' -> 65 to 90==
- ASCII from =='a' o 'z' -> 97 to 122==
- ASCII from =='0' to '9' -> 48 to 57==



### Comments
- Line of code ignore by compiler while executing
- Useful for us as a reference not for compiler
- Documenting the code to someone understand what exactly the code is doing
```code
  // single line comment
  
  /*
  ABC
  DEF
  ...
  ...
  XYZ
  */
```



### Functions
$ f(x) = x^2^ + 2x + 1









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
