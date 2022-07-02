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
