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
           
            mid = (start+end)/2 
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
