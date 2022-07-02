# SORTING
***
- Before Sorting no pattern of numbers/elements in the array
- After Sorting there is a Pattern of numbers/elements
```[2,3,8,5,7] ----->Certain Pattern in Ascending & Descending order```

- **Ascending Order** - ```[2,3,5,7,8] or ['a','b','c','d']```
- **Descending Order** - ```[8,7,5,3,2] or ['d','c','b','a']```

#### Two Sum in an Array
***
```Java
//Two sum in an array
//Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		//input arr
		int[] arr = new int[n];
		for(int i=0; i<n; i++){
		    arr[i]=sc.nextInt();
		}
		//input target
		int target = sc.nextInt();
		System.out.println(Arrays.toString(twoSum(arr,target)));
		
	}
	
	 public static int[] twoSum(int[] nums, int target) {
        int n=nums.length;
        int[] result = {-1,-1};
        //lookimg for sum of two element in arr
        for(int i=0; i<n; i++){
            for(int j=i+1; j<n; j++){
                if(nums[i]+nums[j]==target){
                    result[0]=i;
                    result[1]=j;
                    return result;
                }
            }
        }
        return result;
    }
}
```

# 1. Bubble Sort
***
- There is a pond in village, when we throw the Stone in it the heaviest stone goes deep inside the surface at last and bubble is generated.
- Heavist element goest to its last posion rest lighter is a
```
arr = [8,5,7,3,2]
 Itr1  
  8    5    5   5    5
  5    8    7   7    7
  7    7    8   3    3
  3    3    3   8    2
  2    2    2   2    8
Ist pass of bubble sort has been perform on the given array
Now 8 is its correct position
arr = [5,7,3,2,8]
5  5  5  5
7  7  3  3
3  3  7  2
2  2  2  7
8  8  8  8
IInd Pass of bubble sort has been performed
Now 7, 8 are on its correct position

arr = [5,3,2,7,8]

5  3  3
3  5  2
2  2  5
7  7  7
8  8  8
IIIrd Pass of bubble sort has been performed
Now 5,7,8 are on its correct position

arr = [3,2,5,7,8]

3  2
2  3
5  5
7  7
8  8
IVth pass of bubble sort has been performed
Now We can say every elemt of array is sorted
arr = [2,3,5,7,8]

For n elements -> (n-1) pass
1st pass -> (n-1) comparision
2nd pass -> (n-2) comparision
3rd Pass -> (n-3) comparision
....         ....
....         ....
....         ....
(n-1) pass     1 comparision
------------------------------
               n(n-1)/2 ==> O(n^2)
```

- Num of comparision = n(n-1)/2 = O(n^2)
- Num of Swaps     =  n(n-1)/2  = O(n^2)

```Java
   import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
	
		int[] arr = new int[n];
		for(int i=0; i<n; i++){
		    arr[i]=sc.nextInt();
		}
		bubbleSort(arr);
		System.out.println(Arrays.toString(arr));
		
	}
	
	 public static void bubbleSort(int[] arr) {
        int n=arr.length;
        
        for(int i=0; i<n-1; i++){  //j<n-1-i
            for(int j=0; j<n-1; j++){
                if(arr[j]>arr[j+1]){
                    int temp=arr[j];
                    arr[j]=arr[j+1];
                    arr[j+1]=temp;
                }
            }
        }
        
    }
}
```
- ***Time Complexity = O(n^2) || Space Complexity = O(1)***
- **Worst case** -> even if the array is sorted it will took O(n^2)

### **Stable Sorting Algorithm**
- Relative position of the element 
 ``` [1,2,8*,7,8] ---sorting---> [1,2,7,8*,8] Here Relative position of 8* & 8 are not change after sorting So It's Stable sorting```
 ``` [1,2*,3,2**,8,2**,7]   ---sorting---> [1,2**,2***,2*,3,7,8] Here relative position 2 are change after sorting So, It's unstable sorting```
 - Utility of Stability
   - If two person having same name then arrival time will be consider with first come first serve
   
### **Adaptive Sorting Algorithm**
- If array is already sorted then It should take lesser time to sort
- If array is unsorted than it will took more time

- We can make Bubble Sort Adaptive
```Java
    import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
	
		int[] arr = new int[n];
		for(int i=0; i<n; i++){
		    arr[i]=sc.nextInt();
		}
		bubbleSort(arr);
		System.out.println(Arrays.toString(arr));
		
	}
	
	 public static void bubbleSort(int[] arr) {
        int n=arr.length;
       
        for(int i=0; i<n-1-i; i++){  //j<n-1-i
	    int flag = 0;
            for(int j=0; j<n-1; j++){
                if(arr[j]>arr[j+1]){
                    int temp=arr[j];
                    arr[j]=arr[j+1];
                    arr[j+1]=temp;
		     flag=1;
                }
                if(flag==0){
                    break;
                }
            }
        }
        
    }
}

```

- Arrays.sort() uses dual pivot kind of Hybrid Algorithm which took O(nlogN)
- Why we need to write our own sorting?
  - In Java built in sorting, we have no control over that we we use Arrays.sort() all elements got sorted.
  - Suppose we need Kth Largest element of an Array
  - 1st Largest element = arr[n-1];
  - 2nd Largest element = arr[n-2];
  - So, I would take Kth pass for Kth Largest element O(n*k)

```Java
//Kth Largest element and Kth Smallest element of an array

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int n = sc.nextInt();
	    int[] arr = new int[n];
	    for(int i=0; i<n; i++){
	        arr[i]=sc.nextInt();
	    }
	    int k = sc.nextInt();
	    
		System.out.println(kthLargest(arr,k));
		System.out.println(kthSmallest(arr,k));
	}
	
	public static int kthLargest(int[] arr,int k){
	    Arrays.sort(arr);
	    //Kth largest element in sorted array is arr[n-k]th
	    return arr[arr.length-k];
	    
	}
	
	public static int kthSmallest(int[] arr, int k){
	    Arrays.sort(arr);
	    //Kth smallest element in sorted array in arr[k-1]
	    return arr[k-1];
	}
}

```


## **INSERTION SORT**
***
- Insert element at the correct position in the already sorted array left side
- Pick up element one by one and insert it into already sorted array with thier correct position
- For n element in array (n-1) insertion

```
[8,5,7,3,2]
[8] 5
[5,8] 7
[5,7,8] 3
[3,5,7,8] 2
[2,3,5,7,8]
```
```Java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int n = sc.nextInt();
	    int[] arr = new int[n];
	    for(int i=0; i<n; i++){
	        arr[i]=sc.nextInt();
	    }
	    
	    insertionSort(arr);
	    System.out.println(Arrays.toString(arr));
	}
	
	public static void insertionSort(int[] arr){
	    // i start from 1 bcuz a single element is already sorted
	    int n = arr.length;
	    for(int i=1; i<n; i++){
	        int x = arr[i];
	        int j = i-1;
	        //here we can't interchange condition otherwise runtime error 
		// while(arr[j]>x && j>-1)
	        while(j>-1 && arr[j]>x){       // j must be greater than  -1 otherwise IndexOutOfBound
	            arr[j+1]=arr[j];
	            j--;
	        }
	        arr[j+1]=x;
	    }
	    
	}
	
}

```
```
for n lements ----> (n-1) insertion
1 comparision
2 comparision
3 Comparision
...
...
...
n-1 Comparision
-------------------------------
1+2+3+......+(n-1) = n(n-1)/2
-------------------------------
O(n^2)
```
> **Why sorting? If you don't apply sorting you find endup with higher time complexity.**

> ***Something looks wonderful on paper But It's not granted in reality!***

- **Stability**
  - Insertion Sort is not adaptive because the condition that we pass like arr[j]>x by including arr[j]>=x we can make it adaptive

- **Adaptibility**
  - Insertion Sort by itself Adaptive 

```Java
  int[] arr = {5,8,9,1,4,6,7};

  for(int i=1; i<n; i++){
     int x = arr[i];
     int j = i-1; 
     while(arr[j]>x){   // j>-1
         arr[j+1]=arr[j];
	 j--;
     }
     // j+1 is the correct index for x
     arr[j+1]=x;
     
     System.out.println(Arrays.toString(arr));
  }
```



## SELECTION SORT
***
- We select an index and we find the correct number that should be at that index

```
[1,4,2,5,3]
 0 1 2 3 4
 
 for index 0 = whatever minimum element of the array should be at index 0
 now at index 0 there is a correct element
 for index 1 = what ever the min element in remaining element in the array
 [1,4,2,5,3]       min=1
 [1] [4,2,5,3]     min=2
 [1,2] [4,5,3]     min=3
 [1,2,3] [4,5]     min=4
 [1,2,3,4] [5]     min=5 even if there is a single element already it's minimun in itself
 
 
 - - - - (_) last one is already it should be at correct position
 
 For n elements ----> (n-1) pass
 
```

```
[1,4,2,5,3]
minIndex=i
swap(arr[i],arr[minIndex])

minIndex,i,j starts from 0
           [1, 4, 2, 5, 3]
            0  1  2  3  4
	    
  if( arr[j] < arr[minIndex] )
            minIndex=j;
	    
```
> 1. In Selection sort, i will find element for all indices 0,1,2,3.....n-1
> 2. I look for the minimum element in between [i---->n-1]
> 3. put at the index i = min element

```java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int n = sc.nextInt();
	    int[] arr = new int[n];
	    for(int i=0; i<n; i++){
	        arr[i]=sc.nextInt();
	    }
	    
	    selectionSort(arr);
	    System.out.println(Arrays.toString(arr));
	}
	
	public static void selectionSort(int[] arr){
	    int n=arr.length;
	    //minIndex
	    for(int i=0; i<n; i++){
	        int minIndex=i;
	        for(int j=i+1; j<n; j++){
	            if(arr[j]<arr[minIndex]){
	                minIndex=j;
	            }
	        }
	       //swap(arr[i],arr[minIndex])
	       // minIndex is storing the index of min element that is present (i to n-1)
	       int temp = arr[i];
	       arr[i] = arr[minIndex];
	       arr[minIndex] = temp;
              // 1st pass has been completed
	      //System.out.println(Array.sort(arr));
	    }
	    
	    
	}
	
}
```
- Selection Sort has minimize the Swapping
```
   1+2+3+......+(n-1) = n(n-1)/2  = O(n^2)
   
   (n-1) swaps ---> O(n) Costly Operation
```

- Write an algorithm so that minimize the swap
  - Always use Selection sort
  
- Selection sort is **Non-Adaptive**
- How can  we make Selection Sort Adaptive?

- Selection Sort is **Not Stable**


## MERGE SORT
***
- Merge Sort is a sorting technique that will use **Recursion**

```
MERGING
  A = [2,10,18,20,23]    | m size
  B = [4,9,19,25]        | n size
  Merge this 2 sorted array into a 3rd Array
  
  C = [2,4,9,10,18,19,20,23,25]   | (m+n) size
  
     A      B      C
  i   2     j  4   k   2
  i   10    j  9   k   4
  i   18    j  19  k   9
  i   20    j  25  k   10
  i   23           k   18
                   k   19
i exhauseted       k   20
		   k   23
		   k   25
```

```Java
// Merging Two Sorted Array in third Array

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int m = sc.nextInt();
	    int[] A = new int[m];
	    for(int i=0; i<m; i++){
	        A[i]=sc.nextInt();
	    }
	    
	    int n = sc.nextInt();
	    int[] B = new int[n];
	    for(int i=0; i<n; i++){
	        B[i]=sc.nextInt();
	    }
	    
	    int[] C = new int[m+n];
	    //System.out.println(Arrays.toString(C));
	    merge(A,B,C);
	    System.out.println(Arrays.toString(C));
	}
	
	public static void merge(int[] A, int[] B, int[] C){
	    int m=A.length;
	    int n=B.length;
	    
	    int i=0;
	    int j=0;
	    int k=0;
	    
	    while(i<m && j<n){
	        if(A[i]<B[j]){
	            C[k]=A[i];
	            i++;
	            k++;
	        }
	        else{
	            C[k]=B[j];
	            j++;// C[k++]=B[j++]
	            k++;//
	        }
	    }
	    //Extra elements are also consider
	    while(i<m){
	        C[k++]=A[i++];
	    }
	    
	    while(j<n){
	        C[k++]=B[j++];
	    }
	    
	   
	}
	
}

```


```
             l            mid              h
[..........][2,  5,  8,  12,  3,  6,  7,  10 ][............]
[l->mid]                |mid|                       [mid+1->h]
```

```Java
   
```

- **Non Adaptive because even if sorted take O(nlogN)**
- **Stability depends on if(A[i]<=A[j])**
> ***Recurrence Relation T(n) = 2T(n/2) + O(n)***
> 2T=n/2+n/2   &&   O(n) merging


###  Sum
```java
  //
   int[] arr  = {3,4,2,1,5};
   int sum=10;
   Arrays.sort(arr);
   int ans=0;
   int sum1=0;
   for(int i:arr){
      sum+=i;
      if(sum<=sum1){
          ans++;
      }
      else{
         break;
      }
   }
   System.out.println(ans);
   
   // Arrays.sort() || O(nlogn)
   // for(i : arr)  || O(n)
   //  --------------------
   //                 O(nlogn+n)=O(nlogn)
```


### Buy Sell Stock
***
- Best Time to Buy & sell stock on leetcode
- ```100 180 260 310 535 695```
```Java

```


## QUICK SORT
***
- Can you go stand with your correct position
```   
             ^
          ^  |
       ^  |  |
   ^   |  |  |
 ^ |   |  |  |
```

```
    l              h
  [ 4  3  1  2  8  9 ]
pivot=4
        pivot_index
[1 3 2]   4    [8 9]

```

```Java
void qSort(int[] A, int l, int h){
     if(l<h){
        int p=partition(A,l,h);
	qSort(A,l,P-1);
	qSort(A,P+1,h);
     }
}

public Static int partition(int[] arr,int l,int h){
        int pivot=arr[start];
	int i=start;
	int j=end;
	while(i<j){
	   while(i<=end && arr[i]<=pivot){
	         i++;
	   }
	   while(arr[j]>pivot){
	         j--;   
	   }
        }
	
	if(i<j){
	    int temp=arr[i];
	    arr[i]=arr[j];
	    arr[j]=temp;
	}
}
arr[start]=arr[j];
arr[j]=pivot;
return j;
```

```Java
   public static void qs(int[] arr,int start,int end){
         if(start>=end){
	      return;
	 }
	 //start<end
	 int p = partition(arr,start,end);
	 qs(arr,start,p-1);
	 qs(arr,p+1,end);
	  
   }
```

- O(nlogn)
- General people go for Randomized QS
```
   int randomIndex = (start+end)/2;
   int pivot = arr[randomIndex];
   swap(arr[start],arr[randomIndex]);
```

```Java
    import java.util.*;
    Public class Main{
        public static void main(String[] args){
	     Arrays.sort(arr);//nlogn
	     System.out.println(Arrays.toString(arr));
	}
    }
```

- **T(N)=O(n)}+2T(n/2)**
- **T(N)=O(n)+T(n-1)**

## Counting Sort

```Java
   import java.util.*;


public class Main
{
	public static void main(String[] args) {
	    Scanner sc = new Scanner(System.in);
	    int n = sc.nextInt();
	    int[] arr = new int[n];
	    for(int i=0; i<n; i++){
	        arr[i]=sc.nextInt();
	    }
		countSort(arr);
	}
	
	public static void countSort(int[] arr){
	    int c1=0,c2=0,c3=0;
	    for(int i=0; i<arr.length; i++){
	        if(arr[i]==1){
	            c1++;
	        }
	        else if(arr[i]==2){
	            c2++;
	        }
	        else{
	            c3++;
	        }
	    }
	    System.out.println(c1+" "+c2+" "+c3);
	    int[] brr=new int[arr.length];
	    int k=0;
	    while(k<c1){
	        brr[k++]=1;
	    }
	    while(k<c1+c2){
	        brr[k++]=2;
	    }
	    while(k<c1+c2+c3){
	        brr[k++]=3;
	    }
	    System.out.println(Arrays.toString(brr));
	}
	
}

```
