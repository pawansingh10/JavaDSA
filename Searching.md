# Searching
***
### 1. Linear Search 
* Search in a linear fashion
* Time Complexity O(N)
```Java
   int[] arr = {3,5,8,9,11};
   int target = 8;
   int index=-1;
   for(int i=0; i<arr.length; i++)
   {
       if(arr[i]==target)
       {
         index=i;
       }
   }
   System.out.print(index);
```

### 2. Binary Search
* Searching by dividing the array by n/2 every time
* Array must be in sorted order
* Left=0, right=n; mid=(l+r)/2 concept
* Time Complexity - O(logN)
```Java
  int[] arr = {1,2,3,4,5,6,8};
  int target = 8;
  int index = -1;
  int l = 0;
  int r = arr.length-1;
  while(l<=r)
  {
     int mid=(l+r)/2;
     if(arr[mid]==target)
     {
        index=mid;
	break;
     }
     else if(arr[mid]>target)
     {
        r=mid-1;
     }
     else
     {
        l=mid+1;
     }
   } 
     System.out.println(index);
```
### Important Notions of BS
- ```Complexity will be limit to O(logn)```
- ```Sorted Array will be given that means you have to use BS```
- ```Binary search on answers, high level question actually given array is not sorted still it will use binary search```
- ```Sometimes it overflows due to range mid=(l+r)/2 so at that time prefer mid=l+(r-l)/2;```

```Java
   //Binary Search on Reverse Sorted Array

public class Main
{
	public static void main(String[] args) {
	   int[] arr = {19, 17, 13, 11, 8, 6, 5};
	   int target = 8;
	   System.out.println(bSearch(arr, target));
	    
	}
	public static int bSearch(int[] arr, int target){
	    int end=arr.length-1;
	    int start  = 0;
	    while(start<=end){
	        int mid=(start+end)/2;
	        if(arr[mid]==target){
	            return mid;
	        }
	        else if(arr[mid]>target){
	            start=mid+1;
	        }
	        else{
	            end=mid-1;
	        }
	        
	    }
	    return -1;
	}
}
```

## Binary Search - Iteratively && Recursively
```Java
import java.util.*;
import java.lang.*;
import java.io.*;

public class Main
{
	public static void main (String[] args) throws java.lang.Exception
	{
	  Scanner sc=new Scanner(System.in);
      int n = sc.nextInt();
      int target = sc.nextInt();
      int[] arr = new int[n];
      for(int i=0; i<n; i++){
        arr[i]=sc.nextInt();
      }
      //binarySearch Iteratively
      System.out.println(bs(arr,target,0, arr.length-1));
      //binarySearch Recursively
      System.out.println(bSearch(arr,target,0, arr.length-1));
	}

  public static int bs(int[] arr, int target){
    int l=arr.length;
    int start=0;
    int end=l-1;
    while(start<=end){
      int mid = (start+end)/2;
      if(arr[mid]==target){
        return mid;
      }
      else if(arr[mid]<target){
        start=mid+1;
      }
      else{
        end=mid-1;
      }
    }
    return -1;
    
  }
  
  public static int bSearch(int[] arr, int target, int start, int end){
      if(start>end){
          return -1;
      }
      int mid = start+(end-start)/2;
      if(arr[mid]<target){
          return bSearch(arr,target,mid+1,end);
      }
      else if(arr[mid]>target){
          return bSearch(arr,target,start,mid-1);
      }
      else{
          return mid;
      }
  }
}

```

