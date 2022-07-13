# Stack 
***
- **LIFO** special property
  - Last In First Out
  - ``` 4 -> 3 -> 2 -> 1 ```
  - ``` 4 <- 3 <- 2 <- 1 ```
```
  Insertion & Deletion both at the same end which is top
  
             |___|
      top--> |_4_| <--top
      top--> |_3_| <--top
      top--> |_2_| <--top
      top--> |_1_| <--top
```

* Application of Stack
  - Open Google -> linkedIn.com -> Profile -> profilePicture
  - Open Google -> linkedIn.com->Profile <-
  - Open Google -> linkedIn.com <-
  - Open Google <-
  - <-

  - Text = "abcd.."

- Operations
1. push()  -> insert an element at top
2. pop()   -> delete an element from top
3. peak()  -> return top elemet
4. empty() -> return true if stack is empty else false
> All operation are performed in O(1)

## Stack implementation 
1. By using Array
```java
//Array implementation using Array
class Stack{
    private int[] arr = new int[100];
    private int top =-1;
    
    //push method
    void push(int val){
        if(top==-1){
            arr[++top]=val;
        }
        else{
            arr[++top]=val;
        }
    }
    //pop method
    int pop(){
        int x=-1;
        if(top==-1){
            System.out.println("No element in stack");
            return x;
        }
        else{
            x=arr[top];
            top--;
            return x;
        }
    }
    //peak method
    int peak(){
        if(top==-1){
            return -1;
        }
        return arr[top];
    }
    
    //empty method
    boolean empty(){
        if(top==-1){
            return true;
        }
        return false;
    }
    
    //print method
    void printStack(){
        if(top==-1){
            System.out.println("No Element in Stack");
            return;
        }
        else{
            int x=top;
            while(x!=-1){
                System.out.print(arr[x--]+" ");
            }
            System.out.println();
        }
    }
    
}

public class Main
{
	public static void main(String[] args) {
		Stack s = new Stack();
		System.out.println(s.empty());
		s.push(1);
		s.push(2);
		s.push(3);
		s.printStack();
		s.push(4);
		s.printStack();
		System.out.println(s.peak());
		System.out.println(s.empty());
	}
}

```
2. By using LinkedList
```java
class Node{
    int data;
    Node next;
    Node(int val){
        data=val;
    }
}

class Stack{
    Node top;
    
    void push(int val){
        Node newNode = new Node(val);
        Node temp = null;
        if(top==null){
            top=newNode;
            top.next=temp;
        }
        else{
            temp=top;
            top=newNode;
            top.next=temp;
        }
    }
    
    int pop(){
        Node temp;
        if(top==null){
            return -1;
        }
        else{
            temp=top;
            top=top.next;
            return temp.data;
        }
    }
    
    boolean peek(){
        if(top==null){
            return true;
        }
        return false;
    }
    
    boolean empty(){
        if(top==null){
            return true;
        }
        return false;
    }
    
    void printStack(){
        Node temp=top;
        while(temp!=null){
            System.out.print(temp.data+" ");
            temp=temp.next;
        }
        System.out.println();
    }
}


public class Main
{
	public static void main(String[] args) {
	    Stack s = new Stack();
		System.out.println(s.empty());
		s.push(1);
		s.push(2);
		s.printStack();
		s.push(3);
		s.push(4);
		s.printStack();
		System.out.println(s.pop());
		s.printStack();
		System.out.println(s.peek());
		System.out.println(s.empty());
	}
}


```


## Validate Paranthesis Leetcode 20
***
1. Open Braces push it into Stack
2. Closing Braces -> See top of the Stack
3. If match pop();
4. if(st.empty) then it's Balance

```Java
   int n = s.length();
   Stack <Character> st = new Stack<>();
   
   for(int i=0; i<n; i++){
      char ch = s.charAt(i);
      if(ch=='(' || ch=='{' || ch=='['){
          st.push(ch);
      }
      else{
          if(st.empty()){
	      return false;
	  }
	  else{
	      if(match(st.peek(),ch)){
	          st.pop();
	      }
	      else{
	          return false;
	      }
	  }
      }
      
   }
   
   if(st.empty()){
       return true;
   }
   
   private boolean match(char a, char b){
        if(a=='(' && b==')'){
	       return true;
	}
	if(a=='{' && b=='}'){
	       return true;
	}
	if(a=='[' && b==']'){
	       return true;
	}
	return false;
	
   }
   return false;
```

```Java
  import java.util.*;
  
  public class Main{
      public static void main(String[] args){
         String s = "[]()";
	 System.out.println(isValid(s));
      }
      
      public static boolean isValid(String s){
            if(s.length()%2!=0){
       	        return false;
	    }
	    
	    Stack<Character> st = new Stack<>();
	    for(char ch : s.toCharArray()){
	        if(ch=='(' || ch=='{' || ch=='['){
		     st.push(ch);
		}
		else if(ch==')' && !st.isEmpty() && st.peek()=='('){
		     st.pop();
		}
		else if(ch=='}' && !st.isEmpty() && st.peek()=='{'){
		     st.pop();
		}
		else if(ch==']' && !st.isEmpty() && st.peek()=='['){
		     st.pop();
		}
	    }
	    
	    if(st.isEmpty()){
	        return true;
	    }
	    else{
	        return false;
	    }
      }
  }
```

> Don't leave DSA lifelong
> DSA judges Cognitive Thinking 
> System design | System Design Document

## Leetcode - 1047 Remove All Adjacent Duplicates in Strong
```
   abbaca -> aaca -> ca
   azxxzy -> azzy -> ay
     
```
- ![image](https://user-images.githubusercontent.com/47448422/178801156-2b5cab9a-7511-4d38-a6a3-856fa6428f5a.png)




# Java -> Immutable String
```
  String s = "abc";
  String t = "abc";
  
  String Pool    
  |  s --> "abc"   |
  |        ^       |
  |        |       |
  |        t       |
  s -> "abcd"
  
  String Literals 
```

## Next Greater Element - GFG  || UBER Stack Imp Question
```
 [ 1  3  2  4 ]
   3  4  4  -1
 
 O(n^2)
 
 for(int i=0; i<n; i++)
 {
    for(int j=i+1; j<n; j++)
    {
       if(a[i]>a[j])
           ans[i]=a[j];
    }
     
 }
```

* **NGR - Next Greater Element to Right***
* ***NGL - Next Greater Element to Left*** 
* ***NSR - Next Smaller Element to Right***
* ***NSL - Next Smaller Element to Left***
