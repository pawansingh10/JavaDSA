# Binary Search
- If you Don't know Binary Search, they you will be waiting in Queues of n like others even if your life is sorted
- Sorted -> Binary Search
- If Sorted array is given then it means we can reduce the complexity by using Binary Search

1. Binary Search
2. Ordered Agnostic Binary Search
3. First and Last occurence of an element in sorted array
4. Count of an element in sorted array
5. Number of times the array is rotated
6. Find the Element in rotated sorted array
7. Searching in nearly sorted array
8. Floor & Ceil of an Element
9. Next Letter
10. Index of last 1 in a sorted array
11. Find the position of an element in infinite sorted array
12. Minimum difference element in the sorted array
13. Bitonic Element Maximum element
14. Search in a bitonic array
15. Search in a row wise & column wise sorted matrix
16. Find the element in a sorted array that appears only once
17. Allocate minimum num of pages 

> Binary Search on Answers - High Level Concepts, Given array is not sorted even though we use Binary Search

## 1. Binary Search
```Bash
            0  1  2  3  4  5  6  7  8  9
    arr[] = 1  2  3  4  5  6  7  8  9  10
    target = 8
    
         SORTED
         
      Start                            End
                     Mid
           
            mid = (start+end)/2  ||  mid = start - (start - end)/2;  to control overflow in case of two big int num join resultant would exceed the limit
       (i)  arr[mid] < target then Start=mid+1
       (ii) arr[mid] > target then End=mid-1
       (iii) arr[mid] == target then ans=mid
       
       Complexity O(logn)
```
```Java
public class Main
{
	public static void main(String[] args) {
	    int[] arr = {2,3,4,6,8,9,12};
	    int target=9;
	    //System.out.println(bS(arr,target));
	    System.out.println(BinarySearch(arr,target,0,arr.length-1));
	}
	//Binary Search Iteratively
	public static int bS(int[] arr,int target){
	    int len = arr.length;
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            return mid;
	        }
	    }
	    return -1;
	}
	
	//Binary Search Recursively
       public static int BinarySearch(int[] arr, int target, int start, int end){
           if(start<=end){
               int mid = (start+end)/2;
            
               if(arr[mid]<target){
                    start=mid+1;
                    return BinarySearch(arr,target,start,end);
               }
               else if(arr[mid]>target){
                    end=mid-1;
                    return BinarySearch(arr,target,start,end);
               }
               else{
                    return mid;
               }
          }
          else{
            return -1;
         }
    }
}
```

## 2. Binary Search on Reverse Sorted Array
```Java
public class Main
{
     public static void main(String[] args) {
	    int[] arr = {19, 13, 11, 9, 7, 6, 5};
		int target=5;
		System.out.println(bS(arr,target));
		System.out.println(BinarySearch(arr,target,0,arr.length-1));
	}
	//Binary Search Iteratively
	public static int bS(int[] arr,int target){
	    int len = arr.length;
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]>target){
	            start=mid+1;
	        }
	        else if(arr[mid]<target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            return mid;
	        }
	    }
	    return -1;
	}
	
	//Binary Search Recursively
        public static int BinarySearch(int[] arr, int target, int start, int end){
        
        if(start<=end){
            int mid = (start+end)/2;
            
            if(arr[mid]>target){
                start=mid+1;
                return BinarySearch(arr,target,start,end);
            }
            else if(arr[mid]<target){
                end=mid-1;
                return BinarySearch(arr,target,start,end);
            }
            else{
                return mid;
            }
        }
        else{
            return -1;
        }
    }
}
```

## 4. Search in unknown sorted array i.e Order Agnostic Search
```
   if array size == 1 then no need to check it's in asc or desc
   else if  arr[0] > arr[1] -> desc
   else if  arr[0] < arr[1] -> asc
```
```Java
public class Main
{
	public static void main(String[] args) {
	    //int[] arr = {19, 13, 11, 9, 7, 6, 5};
	    int[] arr = {1,2,4,5,7,9};
		int target=5;
		if(arr.length==1){
		    System.out.println(ascBS(arr,target));
		}
		else{
		    if(arr[0]>arr[1]){
		        System.out.println(descBS(arr,target));
		    }
		    else if(arr[0]<arr[1]){
		        System.out.println(ascBS(arr,target));
		    }
		}
		 
		
	}
	//Binary Search Descending
	public static int descBS(int[] arr,int target){
	    int len = arr.length;
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]>target){
	            start=mid+1;
	        }
	        else if(arr[mid]<target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            return mid;
	        }
	    }
	    return -1;
	}
	//Binary Search Descending
	public static int ascBS(int[] arr,int target){
	    int len = arr.length;
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            return mid;
	        }
	    }
	    return -1;
	}
	
}

```


## 5. First and Last Occurence of an element
```Java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    int[] arr = {1,2,4,5,7,7,7,7,9};
		int target=7;
		int[] ans = new int[2];
		ans=firstLastOcc(arr,target);
		System.out.println(Arrays.toString(ans));
		
	}
	//First last occ
	public static int[] firstLastOcc(int[] arr,int target){
	    int len = arr.length;
	    int[] ans = {-1,-1};
	    //first occ
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            ans[0]=mid;
	            end=mid-1;
	        }
	    }
	    
	    //second occ
	    start = 0;
	    end = len-1;
	    while(start<=end){
	        int mid = (start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            ans[1]=mid;
	            start=mid+1;
	        }
	    }
	    
	    return ans;
	}
	
}
```

## 6. Count of an element in a sorted array
```Bash 
   1. Find first & last occ
   2. Last_occ - First_occ + 1 == count
```
```Java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    int[] arr = {1,2,4,5,7,7,7,7,9};
		int target=7;
		int[] ans = new int[2];
		ans=firstLastOcc(arr,target);
		System.out.println((ans[1]-ans[0])+1);
		
	}
	//First last occ
	public static int[] firstLastOcc(int[] arr,int target){
	    int len = arr.length;
	    int[] ans = {-1,-1};
	    //first occ
	    int start = 0;
	    int end = len-1;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            ans[0]=mid;
	            end=mid-1;
	        }
	    }
	    
	    //second occ
	    start = 0;
	    end = len-1;
	    while(start<=end){
	        int mid = (start+end)/2;
	        if(arr[mid]<target){
	            start=mid+1;
	        }
	        else if(arr[mid]>target){
	            end=mid-1;
	        }
	        else{
	            //arr[mid]==target
	            ans[1]=mid;
	            start=mid+1;
	        }
	    }
	    
	    return ans;
	}
	
}

```

## 7. # of times a sorted array is rotated
- Imp Problem statement


```Bash
    0 1 2 3 4  5  6   7
   [2 5 6 8 11 12 15 18]
   
    0   1  2  3 4 5 6 7
   [11 12 15 18 2 5 6 8]
   How many #of time array rotated?
   - Basically num of time array rotated is dependent on min element's index
   min_element idx = 0 rotation 0time
   
   2 5 6 8 11 12 15 18 -> Rotation0  index 0
   5 6 8 11 12 15 18 2 -> Rotation1  index 7 
   6 8 11 12 15 18 2 5 -> Rotation2  index 6     
   8 11 12 15 18 2 5 6 -> Rotation3  index 5
   11 12 15 18 2 5 6 8 -> Rotation4  index 4
   
   Number of rotation = index of min element
   So, Find the index of minimum element 
   1. Linear Search O(n)
   2. Since Array is sorted so better to use BS O(logn)
   
   General Binary Search -> arr[] target find index
   Here target is minimum element 
   
   start                   end
             mid
   minelement would be smaller than both neighbour
   if(arr[mid]==x)
   
```
```Java

```
