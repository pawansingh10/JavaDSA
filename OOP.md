# OOP - Object Oriented Programming
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
