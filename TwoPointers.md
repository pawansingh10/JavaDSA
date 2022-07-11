## Two Pointers Algorithm
***
1. Fast & Slow
2. Floyd Cycle Detection
3. Binary Search
4. Merge / Merge Sort
5. Quick Sort / Partitions

> Note : - Arrays.sort() -> O(nlogN)

## Two Sum Leetcode
***
```
  [1,2,3,4,8,15,25,30]   target = 18
                   [3,15]==target
                    x,y
``` 
- 1. BruteForce
  - 2 Nested Loop
  - O(n^2)
```Java
int[] arr = {1,2,3,4,8,14,15,25,30};
int target = 18;
for(int i=0; i<n; i++){
    for(int j=i+1; j<n; j++){
        if(arr[i]+arr[j]==target){
             //
        }
    }
}
        
```

- 2. HashMap Approach
  - alpha + beta == target 
  - beta = target - alpha

- 3. 2Pointer Approach 
   - Array needs to be sorted
```
                          same pair will be repeat in reverse order         26  >  18
    --------------------->|<--------------                                  16  <  18
   i=0;                   |            j=n-1                                17  <  18
   [ 1,  2,  3,  4,  5,  8,  15,  25,  30 ]                                 18  == 18
                          |
                          |
    target = 18
    
     if(arr[i]+arr[j]==target)
     
     if(sum>target){  // sum decrease
          j--;
     }
     else if(sum<target){  // sum increase
          i++;
     }
     else{
         System.out.println(arr[i]+" "+arr[j]);
         i++;
         j--;
     }

    int n = arr.length;
    int i=0;
    int j=n-1;
    while(i<j){
       //
    }
 ```
 
 ## Three Sum Leetcode
 1. O(n^3) -> 3 nested loop
 ```
   arr = [ -1, 0, 1, 2, -1, 4 ]
   target = 0;
   for( int i=0; i<n; i++){
      for(int j=i+1; j<n; j++){
         for(int k=j+1; k<n; k++){
            
         }
      }
   }
   
 ```
 
 2. Two pointer approach o(n^2)
 ```
 Array should be sorted O(nlogn)
        i ->            <- j    
     |
 [ -4, -1, -1, 0, 0, 1, 3, 4 ]
     |
     |
   Target = 0;
   alpha + beta + gamma = 0
   alpha + beta = -gamma
   ____________    ______
       ^             ^
       |             |
    2 Sum Array     loop to decide this value
  [-4, 0, 4 ]
  [-4, 1, 3 ]
  [ 1, 0, 1 ]
 ```
 
 ```Java
    int n = nums.length;
    List<List<Integer>> ans = new ArrayList<>();
    Arrays.sort(nums);
    for(int i=0; i<n-2; i++){
       int target = nums[i];
       int start = i+1;
       int end = n-1;
       //Two Sum Problem
       while(start<end){
           int sum = nums[start]+nums[end];
           if(sum<target){
              start++;
           }
           else if(sum>target){
              end--;
           }
           else{
              List<Integer> l = new ArrayList <Integer> ();
              l.add(nums[i]);
              l.add(nums[start]);
              l.add(nums[end]);
              ans.add(l);
              while(start<end && nums[start]==nums[start+1]){
                 start++;
              }
              start++;
              while(start<end && nums[end]==nums[end-1]){
                  end--;
              }
              end--;
           }
       }
       
       while(i<n-2 && nums[i]==nums[i+1]){
           i++;
       }
    }
 ```


## ArrayList -> Parts of Java Collection Framework
- ArrayList is like C++ vector
- ArrayList mimics the behavior of array
- ArrayList is Dynamic Size Array
- Array's Drawback -> Fixed Size,Insertion, Deletion

```
               Obj
                |
                V
   ArrayList <Integer> arr;
   arr = new ArrayList<>();
                         ^
                         |
                         constructor
   arr = []
   arr.add(5); // 5
   arr.add(6); // [5,6]
   
   arr.size(); // 2
   System.out.println(arr); // [5,6]
   arr.add(index,val);
   arr.add(1,7); // [5,7,6]
   arr.addAll(arr2);//[5,7,6,1,2,3]
   arr.addAll(index,arr);
   arr.get(index);
   arr.get(0); //5
   arr.get(3); //1
   
   Arrays.sort(arr); // for array
   Collections.sort(arr); // for arraylist
   
```
- Wrapper Classes are classes having primitive data type inside it
```Integer Character Float Double```

- Interface
  - Interfaces are like contract -> Only have signature not implementation
  - Interfaces are like contracts that you will be writing
 ```Java
    Interface abc{
         final int a =10;
         int move(); // This method is mandatory to implement in Class
    }
 ```
 ```
    Interface               Interface              Interface
      ^                         ^                      ^
      | implements              | extends              |  extends
      |                         |                      |
    Class                    Interface               Class
 ```

```
Interface
List{
     -----
     -----
     // only signature not implementation
}

class ArrayList implements List{
     //
     //
     // implemenatation here
}

Instantiate a Class
List <Integer> l = new ArrayList<>();
List <Integer> ll = new LinkedList<>();

```


















