# JavaDSA

## DSA by Java Repository 

- ***Success is Vector(Magnitude+Direction)***

### Computer Programming == Computer + Program

### DSA == Data Structure + Algorithm


### Print Hello
***
```Code
public class Main
{
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```

### Variable,Memory
***
- Variable declaration
- Variable Initialization
- variable Assignment


### Data Types
***
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
***
- Collection of pre-written code by developers
- Scanner -> import java.util.scanner;
- System  -> import java.lang.*;
- Math    -> import java.util.math;



### Taking input
***
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
***
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
***
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
***
- UpCastiing -> Automatically
-```int to double ```
- DownCasting -> Manually 
-```double to int```


### Pattern Printing
***





### ARRAYS
***
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
***
- Array of Arrays
- Excelsheet, ChessBoard, ClassRoom
- ```code
  //Sum of black and white in chesscard
  
  int sum=0;
  for(int i=0; i<)
  
```
```code
  //Zig-Zag Trversal of Array
```



### Switch 
***
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
***
- Special character to store every thing
- Capital Letter, Small Letter, Numbers, Symbols
- Computer only understand only 0/1, then how we these values store
- They are store using **ASCII** Universal Standards followed by compiler to use the character
- ASCII from 'A' to 'Z' -> 65 to 90
- ASCII from 'a' o 'z' -> 97 to 122
- ASCII from '0' to '9' -> 48 to 57



### Comments
***
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

### Break and Continue
***
- ```break -> break out of loop```
- ```continue -> Skip everything and go to the next iteration of loop```


### For Each loop
***
```code
   int[] arr = {1,2,3,4,5};
   for(int x : arr)
   {
     System.out.println(x);
   }
```

### Scope of variable
![image](https://user-images.githubusercontent.com/47448422/172049602-dc2b9a1c-66dd-44ee-9dc5-4a73f0503e73.png)

### Functions
***
$ f(x) = x^2 + 2x + 1
- One of the principle people follow in Software Industry is ***DRY==Don't Repeat Yourself***
1. Function reduces the redundency of code
2. Functions makes Debugging easy
3. > **MODULAR** EASIER TO READ,UNDERSTAND AND MAINTAIN THE CODE
4. Quarantine all features 

```code
  return_type function_name(arguments)
  {
    System.out.println("Hello");
    return ;
  }
```

```code
int square(int num)
{
   int ans = num*num;
   return ans;
}

void square1(int num)
{
  System.out.println(num*num);
}
```

> **main() method is the starting point of any java program**
> **Whenever a function call starts a context associated with it created**



### STRING
- Non-Primitive data type because Strings are made up of concatenating multiple character
- Every string is function associated with it
```code
   String str = "Love Everything!"
   str.length(); //16
   str.charAt(0); // L
   str.indexOf('z'); //-1
   str.indexOf('e'); //3
   str.indexOf('e',4); //7 start searching from index 4
   str.indexOf("Love"); //0
   str.indexOf("Love", 5); //-1
   str.toUpperCase();
   str.toLowerCase();
   Character.toUpperCase('o'); // O
```

### Substring Vs Subsequence
***
- **SubArray/SubString/SubSequence**
> ***Continuous part of string is SubsString***
> ***Continuous or non continuous part of string is subsequence, subsequence might not be ordering***
```code
  int[] arr = {1,3,5,7,11,3,5,8];
  subsequence = [3,7,5] // same sequence so subsequence
  subarray    = [3,5,7] // subarray because of continuous
  
  String str = "Hello Java";
  str.subString(3); // gives substring from index 3 till end
  str.subString(1,3); // gives substring from index 1 to 2
  str.replace('e','E'); // replace e to E
```
> ***Strings are immutable, that means whever we modify the string actually the original string is as it is and a new copy of string is created***

```java
   // String pool/String literal Vs String Object
   String s = "Hello My Name"; // String literal
   String s = new String("Hello My Name"); // String obj
   
   s.split(" "); // split the string on the basis of passed delimeter
   
   String [] str = s.split();
   for(String x : str)
   {
      System.out.println(x);
      
   }
   
   //Printing array
   System.out.println(Arrays.toString(str));
   // output ["Hello","My","Name"]
   
   
   
```





### TIME & SPACE COMPLEXITY
***
- ***When Application is deploy in production, millions of users are going to use is. So the Scaling up,Effiecient use of resources and  Effiency of task executions matters a lot because of everything has its cost!***
- Writting Efficient Code in this real healthy competitive market is important for business perspective

```Swiggy Vs Zomato delivery time```
```Payment Gateways while tranferring money```

- RAM is very low in size, very expensive because of made up of semi-conductor
- Time and Space complexity are 2 critical evaluation of a program.

- **Time Complexity** -> Time taken by the program  to run as a function of input
1. **Best Case (Omega)**
2. **Average Case (Theta)**
3. **Worst Case (O))**
```O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(2^n) < O(3^n)```





## Recursion
***
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









## Searching
***
### 1. Linear Search 
* Search in a linear fashion
* Time Complexity O(N)
```Java
   int[] arr = {3,5,8,9,11};
   int target = 8;
   int index=-1;
   for(int i=0; i<arr.length; i++)
   {
       if(arr[i]==target)
       {
         index=i;
       }
   }
   System.out.print(index);
```

### 2. Binary Search
* Searching by dividing the array by n/2 every time
* Array must be in sorted order
* Left=0, right=n; mid=(l+r)/2 concept
* Time Complexity - O(logN)
```Java
  int[] arr = {1,2,3,4,5,6,8};
  int target = 8;
  int index = -1;
  int l = 0;
  int r = arr.length-1;
  while(l<=r)
  {
     int mid=(l+r)/2;
     if(arr[mid]==target)
     {
        index=mid;
	break;
     }
     else if(arr[mid]>target)
     {
        r=mid-1;
     }
     else
     {
        l=mid+1;
     }
   } 
     System.out.println(index);
```
### Important Notions of BS
- ```Complexity will be limit to O(logn)```
- ```Sorted Array will be given that means you have to use BS```
- ```Binary search on answers, high level question actually given array is not sorted still it will use binary search```
- ```Sometimes it overflows due to range mid=(l+r)/2 so at that time prefer mid=l+(r-l)/2;```

```Java
   //Binary Search on Reverse Sorted Array

public class Main
{
	public static void main(String[] args) {
	   int[] arr = {19, 17, 13, 11, 8, 6, 5};
	   int target = 8;
	   System.out.println(bSearch(arr, target));
	    
	}
	public static int bSearch(int[] arr, int target){
	    int end=arr.length-1;
	    int start  = 0;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]==target){
	            return mid;
	        }
	        else if(arr[mid]>target){
	            start=mid+1;
	        }
	        else{
	            end=mid-1;
	        }
	        
	    }
	    return -1;
	}
}
```









































































## OOP - Object Oriented Programming
***
[x] Why OOP?
- OOP is very important principle When we deal with or solve any real life practical problem

> **Software Developer is  expected to know basic of OOP because whenever you work for any company, you have to deal with problems that has pratical usecase**

- Example -> AMAZON Market Place, Sellers upload thier products to Amazon Plaform through code

### 3 Important Characteristics of OOPs that's why use in Practical world
1. OOP makes our program **Moduler**
2. OOP reduce **Redundency**
3. OOP ensure **Data Protection/Privacy**

## Class
- Class is a **Blueprint** or **Template** of How something look like.
- A **.java** file can have atmost 1 (0,1) public class
- Name of Public Class and Name of File should br matching

```Java
// file name should be Main.java
   public class Main
{
	public static void main(String[] args) {
		
	}
}
``` 
- A class doesn't occupy memory by itself
```Java
   public class Main
{
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
	
	Class Person{
	    String name;
	    int age;
	}
	
	Class House{
	    int bedroom;
	    int hall;
	    int kitchen;
	    int windows;
	}
	
	
}
```

## Object
***
- Object is an instance of a Class
- By using object we instantiate the class
```java
   public class Main
{
	public static void main(String[] args) {
		Person p1 = new Person();
		System.out.println(p1.name+" "+p1.age);
	}
	
}

class Person {
	    String name;
	    int age;
}
```
- 	Person p1 = new Person(); -> This function is called Constructor 
> **Constructor is a special method which is responsible for creating an object**

- **Default Constructor**
 - If we do not create any constructor then default constructor of Java will be called & Object will be created.
 - Name of Constructor is same as the name of class

- Object is only created at runtime
- Objects are always present in **Heap-Memory**
- ![image](https://user-images.githubusercontent.com/47448422/174479057-f34ac76f-5a60-43f1-8807-534e6f7f2bb2.png)

### Attributes/Properties
- Only having attributes is not sufficient
### Method/Behavior
```Java
public class Main
{
	public static void main(String[] args) {
		Person p1 = new Person();
		System.out.println(p1.name+" "+p1.age);
		p1.dance();
	}
	
}

class Person {
	    String name;
	    int age;
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
	    }
	    
}
```

## Polymorphism
***
- Poly(many) + Morphism(form)
- Function name is same but taking different different arguments
```Java
   class Person {
	    String name;
	    int age;
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
	    }
	    
	    void dance(int time){
	        System.out.println(name+" has been dancing since "+time+" minutes.");
	    }
}
```
``` If you give to a baby they baby will cry, if you give chocolate baby then baby will smile ```
- Above is the example of Compile Time Polymorphism (Method Overloading)
- because even before run your program compiler knows that there are different types of methods based on arguments pass
- We will see later Run Time Polymorphism (Method Overloading)


## Constructor
***
- Constructor is used to create object
- Constructors don't have return type
- If you don't write your constructor java will provide you default constructor 
- Default constructor takes no argument
- ``` Person p1 = new Person(); ```
- If you want to send name and age as argument definately default constructor will not help
- ``` Person p2 = new Person("Ram",14); ```
- The moment you write your own constructor java default constructor will lost

> **If you don't give any access modifier it will be default**
```Java
   class Person {
	    String name; 
	    int age;
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
	    }
   }
```

## this keyword
***
1. this refers to the object
2. by using this we will set data members and call methods
3. Constructor Chaining

> Note-1: Only the first line can be the constructor call in the Constructor Chaining
> Note-2: There must be at least one constructor which has no other Constructor Call otherwise it would be infinite loop
> Note-3: Chaining can be any order, Ordering is not important

```Java
class Person {
	    String name;
	    int age;
	    //Constructor
	    void Person(String newName, int newAge){
	        name = newName;
	        age  = newAge;
	    }
	    
	    public Person(String name, int age){
	        this.name = name;
	        this.age  = age;
	    }
	    
	    
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
		dance(5);
		
	    }
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
		this.dance(5); //equivalent to dance(6);
		
	    }
	    
	    void dance(int time){
	        System.out.println(name+" has been dancing since "+time+" minutes.");
	    }
}
```

## Static Keyword
***
[x] Count the track of how many objects are created of a class
```Java
public class Main
{
	public static void main(String[] args) {
	  Person p1 = new Person("Abc",22);
	  Person p2 = new Person("Xyz",24);
	  
	  System.out.println(Person.count);
	}
	
}

class Person {
        static int count;
	    String name;
	    int age;
	    
	    Person(String name, int age){
	        this.name=name;
	        this.age=age;
	        count++;
	        dance();
	    }
	    
	    
	    void dance(){
	        System.out.println(name+" is dancing.");
	        this.dance(5);
	    }
	    
	    void dance(int time){
	        System.out.println(name+" has been dancing since "+time+" minutes.");
	    }
}
```
1. Static Variable
```Java static int count; 
        Class.count;
```
2. Static Method
```Java static void abc(){
       System.out.println("Static Method");
    }
    Person.abc();
```

- Why main static?
``` Main method is the Starting point of any java program ```
- because if we need an object to call main method then it is not feasible in this case
- Main method is responsible for creating object
- Static method doesn't require the object to call
``` .java     
    javac      A.class   B.class    ByteCode
    
    JRE call B.main()
```

## Inheritance
***
1. Parent Class
2. Child Class
```Java
   class Person{
         String name;
	 int age;
   }
   
   class Developer{
         String name;
	 int age;
	 String github_user;
   }
   
   class Doctor{
         String name;
	 int age;
	 String degree;
   }
```
- When the Constructor of child class run, first of all Constructor of Parent class be invoked!
```Java
public class Main
{
	public static void main(String[] args) {
	  Person p1 = new Person();
	  Developer dv1 = new Developer();
	  Doctor d1 = new Doctor();
	}
	
}

class Person {
	String name;
	int age;
	
	public Person(){
	    System.out.println("Person has been born");
	}
}

class Developer extends Person{
    String github_user;
    public Developer(){
        System.out.println("Developer has been born");
    }
}

class Doctor extends Person{
    String degree;
    
    public Doctor(){
        System.out.println("Doctor has been born");
    }
}
```

## super Keyword
***
```Java
public class Main
{
	public static void main(String[] args) {
	  Doctor d1 = new Doctor("Dr Abc",24,"MBBS");
	  d1.getdetails();
	}
	
}

class Person {
	String name;
	int age;
	
	public Person(String name, int age){
	    this.name=name;
	    this.age=age;
	}
	
	public void getdetails(){
        System.out.println("Name="+name+" Age="+age);
    }
}

class Doctor extends Person{
    String degree;
    
    public Doctor(String name, int age, String degree){
        //this.name=name;
        //this.age=age;
        super(name,age); //Person(name,age);
        this.degree = degree;
    }
    
    public void getdetails(){
        System.out.println("Name="+name+" Age="+age+" Degree="+degree);
    }
}
```

## Runtime Polymorphism or Dynamic Method Dispatch
***
```Java
public class Main
{
	public static void main(String[] args) {
	  Doctor d1 = new Doctor("Dr Abc",24,"MBBS");
	  d1.getdetails();
	  d1.dance();
	}
	
}

class Person {
	String name;
	int age;
	
	public Person(String name, int age){
	    this.name=name;
	    this.age=age;
	}
	
	public void getdetails(){
        System.out.println("Name="+name+" Age="+age);
    }
    
    public void dance(){
        System.out.println("Person is dancing");
    }
}

class Doctor extends Person{
    String degree;
    
    public Doctor(String name, int age, String degree){
        //this.name=name;
        //this.age=age;
        super(name,age); //Person(name,age);
        this.degree = degree;
    }
    
    public void getdetails(){
        System.out.println("Name="+name+" Age="+age+" Degree="+degree);
    }
    
    // public void dance(){
    //     System.out.println("Doctor is dancing");
    // }
}
```

### final keyword
- Nobody can change/override the final attributes/method
```java final void dance(){
         //
    }
```

```java
   Person p1 = new Person();
   p1.
   
   Doctor d1 = new Doctor();
   d1.
   
   Person p1 = new Doctor();
   // reference to Parent class object, pointed to child class object
   p1.age;
   p1.name;
   p1.dance();//Here Dynamically at runtime decide which dance() method detect
```

> **In Java every class inherits the "Object" class**
> **Types of Inheritance**
1. Single-Level Inheritance
2. Multi-Level Inheritance
3. Hierarchical Inheritance
4. Multiple Inheritance // Doesn't support by Java Diamond Problem
5. Hybrid Inheritance



## OOP-3
![image](https://user-images.githubusercontent.com/47448422/174635100-4518b9b1-f54c-4636-bce8-6bd3440b83a4.png)
