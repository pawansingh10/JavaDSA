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
