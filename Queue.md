# QUEUE
***
- Queue follow **FIFO** properties
  - First In First Out
  - Deletion happens at Front
  - Insertion happens from Rear
```
           BookingCounter
           |_________|
  _________|_________|____________ ...........->p2->p1->p0
             pO
             p1
             p2                pn
             p3               /
             p4              /
             ^             . pn-1
             |           .
             .         .
             <-- . . .
             
```
- Process Scheduling
  - ``` |4|3|2|1| -----> Processor(CPU) 4->3->2->1 ```
- Queue of Requests/Call
  - CPU algorithm **Round Robin**
  - Each process is provided a Time Quantum to reduce the long waiting time of a process
  - For each process having a time quantum in which process start exceuting and once the the Time quantum is over process paused and wait for the next time quantum

- O(1) for operation
```java
  
Queue<Integer> q = new Queue<>();
q.add(); // throw error if overflow || Add at the Rear
q.offer(); // return Null if overflow || Add at the rear
q.peek(); // Front Element
q.size(); // size of the queue
q.remove(); // remove the front
q.poll(); // remove the front

```
- Queue could be implement by-
1. Using Array
2. Using LinkedList

## Queue Implementation using Array
```Java
import java.util.*;

class Queue{
    int[] arr;
    int front;
    int rear;
    Queue(){
        arr = new int[100];
        front = -1;
        rear = -1;
    }
    void offer(int val){
        if(front==-1 && rear==-1){
            front=0;
            rear=0;
            arr[0]=val;
        }
        else{
            arr[++rear]=val;
        }
    
    }
    
    int poll(){
        if(front==-1 && rear==-1){
            return -1;
        }
        int x=arr[front];
        front++;
        return x;
    }
    
    int peek(){
        if(front==-1 && rear==-1){
            return -1;
        }
        return arr[front];
    }
    
    boolean empty(){
        if(front==-1 & rear==-1){
            return true;
        }
        return false;
    }
    
    void printQ(){
        int x=front;
        for(int i=x; i<=rear; i++){
            System.out.print(arr[x++]+" ");
        }
        System.out.println();
    }
}

//Main Class
public class Main
{
	public static void main(String[] args) {
	    Queue q = new Queue();
	    
	    System.out.println(q.peek());
	    System.out.println(q.empty());
	    q.offer(1);
	    q.offer(2);
	    q.printQ();
	    q.offer(3);
	    q.offer(4);
	    q.printQ();
	    q.poll();
	    q.printQ();
	    System.out.println(q.empty());
	    System.out.println(q.peek());
	}
}

```


## Queue Implementation using LinkedList

```Java
  Interface          Interface
   |                     |
   V                     V
Queue<Integer> q = new Queue<Integer>();

 Interface             Class   that implements the Queue interface
   |                     |
   V                     V
Queue<Integer> q = new LinkedList<Integer>();
```

```Java
  
```

## Implement Queue Using Stack --VVImp Classic Question LeetCode 232
- [Implement Queue Using Stack]()

## Implement Stack Using Queues --VVImp Classic Question LeetCode 225
- [225. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)

