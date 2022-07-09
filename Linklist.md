## Lecture 1
## LinkList
***
- Why LinkList? even though we have Arrays
- Pros & Cons with every Data Structure
- Limitation of Arrays
```
RAM Memory
8 Bits = 1 Byte
32 Bits = 4 Bytes i.e required to store an int variable
__________________________________________
 
      |     |     |     |      |    |
__________________________________________

int x ;
x = 5;
  Vs
int[] arr = new int[5];
arr[0],   arr[1],   arr[2],    arr[3],    arr[4]
4 Bytes   4 Bytes    4 Bytes   4 Bytes    4 Bytes
in the case of array here 20 Bytes contiguous memory alloted to array
```
- Suppose we Sufficient Memory avaiable in memory but that's not contiguous then what will we do in that case.
- Memory Defragmentation -> Previously we have data but now data has been deleted to space is free now we can use that.

### Drawback of Arrays
1. Fixed Size - Can't insert more element at runtime
2. Contiguous wastage
3. Insertion Deletion

- ***Linked List is born to handles the flaws of array***

### Node
 - |  Data | Reference to the next node  |
   | :---      |          ---: |
  - **Node** is the Basic building block of LinkList
  - Node is something which we need to define it unlike int beacuse data could be anything object etc etc 

``` Person p = new Person("Ram",14);```
``` p is reference here  new keyword allocate memory```

| Pointer     |             |  Reference Variavle|
| :---        |    :----:   |          ---: |
| Pointer is a variable that store addresses | | Reference Variable just hold references|


## LinkList
```Java
lass Node{
    int data;
    Node next;
    Node(int val){
        data = val;
    }
}
class LinkedList{
    Node head;
    void insert(int val){

        Node newNode = new Node(val);
        if(head==null)
            head = newNode;
        else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;
            }
            temp.next = newNode;
        }
        return;
    }
    void printLL() {
        Node temp = head;
        while(temp!=null){
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class Main {

    public static void main(String[] args) {
       LinkedList ll = new LinkedList();
       ll.insert(2);
       ll.insert(3);
       ll.insert(56);
       ll.insert(412);
       ll.printLL();
       ll.insert(100);
       ll.printLL();
        ll.insert(233);
        ll.insert(536);
        ll.insert(4112);
        ll.printLL();
    }
}

```

## Lecture 2

* LinkedList
  - Better than Array
  - Dynamic Allocation of Memory
 
* Drawback of Array
  - Array -> Fixed Size
  - Contiguous Wastage
  - Insertion & Deletion in array takes O(n)
  
```
                        head                                tail
   [LinkedList] ---->  [[data][ref]]-->[[data][ref]]-->[[data][ref]]-->Null
```

- Program starts executing from the main method
  - ```
     public class Main{
	         public static void main(String[] args) {
		             //Program executions start here
               System.out.println("Hello World");
	         }
     }
    ``` 

```Java
   class Person{
      String name;
      int age;
      String address;
      
      void walk(){
        System.out.println("Walking");
      }
      
   }
```
> **Method won't be executive the moment program is compile or when an object is created but method gets executed when you call this by creating object**
> **Object is Instantiation of a class**
> **Object is Real World Entity**

```
   class is only a blueprint
   ------------------------------------
   Compile -> ByteCode
   ------------------------------------
   public static void main(String[] args){
        //     |       JVM will run this method only
        //     v
   }
   
   
   int[] arr  =  new int[10];
   Person p   =  new Person();
      |             |
      v             v
   ref var         mem location
   p.age=20;
   p.name="Java";
   
   
   [data [[data][ref]] [ref]] [c]
   [[data][ref]]  [v]
   
   Person p  = new Person();
   Person p2 = p;  // both p1 & p2 is pointing to the same 
```

> Note - Wavelength of red high,  Frequency less -> less distorted yellow

```Java
// Node Class
class Node{
   int data;
   Node next; //-->null
   //Constructor
   Node(int val){
        data=val;
   }
   
}

//LinkedList Class

class LinkList{
     Node head;  // data attributes head ref var
                 // head is pointing to null
     void insert(int val){
         Node newNode = new Node(val);//creation of node
         if(head=null){
             head = newNode;
         }
         else{
             Node temp = head;
             while(temp.next!=null){
                 temp=temp.next;
             }
             temp.next=newNode;
         }
         return;
     }
     
     void printll(){
          Node temp=head;
          while(temp!=null){
               System.out.println(temp.data+"->");
               temp=temp.next;
          }
          System.out.println();
     }
     
}

// main Class
public class Main{
   public static void main(String[] args){
        LinkList l1 = new LinkList();
        LinkList l2 = new LinkList();
   }
}
```

```
   null -> undefined or unspecified is called NULL
   temp = null;
   temp pointing to null
   
   Maintain a tail node
   tail     tail    tail  
    |        |       |      
    1------->2------>3---->null
                           
                          tail
    1------->2------>3---->4------>null
    
    We can insert the element in O(1)
```

``` Node next;
    next = new Node();
    
        Vs
        
    int x;
    x = 5;
```



## LinkedList 2.0

```
         head
           1 ---> 2 ---> 3 ---> Null
  head
    0 ---> 1 ---> 2 ---> 3 ---> Null
```
```Java
    void insertAtHead(int val){
        Node temp = new Node(val);
        temp.next = head;
        head = temp;
    }
    //but this will not work for the empty while head is null
    
    void printll(){
        Node temp=head;
        while(temp!=null){
            System.out.println(temp.data+"->");
        }
        System.out.println(temp.data);
    }
    
    
    void deleteFisrtNode(){
       //
    }
    
    
    void deleteAtEnd(int val){
         if(head==null){
             System.out.println("No Nodes");
         }
         else{
             head = head.next;
         }
         while(temp.data!=Val){
              temp=temp.next;
         }
    }
    
    void delete(int val){
         Node prev=null; //default
         Node temp = head;
         if(head==null){
            System.out.println("Value not present");
            return;
         }
         else{
             if(head.data==val){
                 head = head.next;
                 return;
             }
         }
         while(temp!=null && temp.data!=null){
              prev = temp;
              temp = temp.next;
         }
         if(temp==null){
             System.out.println("No value bro");
         }
         else{
             prev.next = temp.next;
         }
         
    }
```


## Lecture 3
- LinkedList is all about Changing the link >> Updating the data
```
     1 ---> 3 ---> 5 ---> 7
             \   /
               4
         
     newNode.next = temp.next;
     temp.next = newNode;
```
```Java
    void insertAfterVal(int val, int node_val){
         Node  newNode = new Node(node_val);
         Node temp = head;
         while(temp.data!=val){
             temp = temp.next;
         }
         if(temp==null){
             System.out.println("Values not present");
         }
         else{
              newNode.next = temp.next;
              temp.next = newNode;
         }
         System.out.println();
      return;
    }
```

## Middle of the LinkedList LeetCode 876
```
  public ListNode middleNode(ListNode head){
      int n=0;
      ListNode temp=head;
      while(temp!=null){
          n++;
          temp=temp.next;
      }
      temp=head;                                     //BRUTE FORCE
      n=n/2;
      while(n>0){
         temp=temp.next;
         n--;
      }
      return temp;
  }
  
  
  // 2 POINTER APPROACH
  
     head
     temp
     fast
      |
      1 --> 2 --> 3 --> 4 --> 5 --> Null
                                   2X
      fast -> 2 place/step   |-----------------|
      slow -> 1 place/step   |---------|
                                  X
      fast = fast.next.next
      { 60KM/hr -> Target
      { 30KM/hr -> middle
      
```
