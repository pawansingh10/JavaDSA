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

- Open Google -> linkedIn.com -> Profile -> profilePicture
- Open Google -> linkedIn.com->Profile <-
- Open Google -> linkedIn.com <-
- Open Google <-
- <-

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

```
