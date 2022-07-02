# Binary Search
***

| Data Structure   | Algorithm | 
| :---        |    :----:   |  
| Array      | Searching       | 
| String   | Sorting        | 
|Stack| Filter|
|Queue| Hashing|
|Graph|        |
| Tree|        |

### MAANG
* Amazon
 1. Resume
 2. Coding Test
 3. Interview Round I - DSA
 4. Interview Round II - DSA
 5. Interview Round III - Project/HM
 6. Interview Round IV - HR

* Microsoft
 1. Resume
 2. Coding Round
 3. DSA Round I
 4. DSA Round II 


## Why we are using searching algorithms even though we have Arrays.sort()?
- Internal Working & Functioning
- Internal Implementation
- Control Over Sorting

## Problem Solving
- Bruteforce O(2^n) -> O(n^2) -> O(n) -> O(logn) -> optimize
- What/Why?

## Sorting
- Bubble Sort O(n^2)
- Selection Sort O(n^2)
- Insertion Sort O(n^2)
- Merge Sort  O(nlogn)
- Quick Sort  O(nlogn)
- Count Sort O(n)

## Count Sort
- a sorting algorithm that sorts the elements of an array by counting the number of occurrences of each unique element in the array
- The count is stored in an auxiliary array and the sorting is done by mapping the count as an index of the auxiliary array.
```code
arr = [1,3,1,2,3,3,1,2,3]
count_of_1 = ~0~ ~1~ ~2~ 3
count_of_2 = ~0~ ~1~ 2
count_of_3 = ~0~ ~1~ ~2~ ~3~ 4
arr = [1,1,1,2,2,3,3,3,3]
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
```Java
System.out.println(c1+" "+c2+" "+c3);
	    int[] brr=new int[arr.length];
	    int k=0;
	    for(int i=0; i<arr.length; i++){
	        if(k<c1){
	            brr[k++]=1;
	        }
	        else if(k<c1+c2){
	            brr[k++]=2;
	        }
	        else{
	            brr[k++]=3;
	        }
	    }
	    System.out.println(Arrays.toString(brr));
```

> **Auxiliary Space Complexity -> Extra Space used by Algorithm to Solve your problem**


# Problems
***
## House Robber
- [HouseRobber](https://leetcode.com/problems/house-robber/)
```
[1,2,3,1]
     1+3=4  -> max value
     2+1=3
    
[2,7,9,3,1]
      2+9+1=12 -> even
      7+3 =12  -> odd
Note - Sum of even indices and odd indices that would be wrong
``` 
```Java
//WRONG APPROACH
int fun(int[] arr){
int sumEven=0;
int sumOdd=0;
for(int i=0; i<n; i++){
   if(i%2==0){
      sumEven+=a[i];
   }
   else{
      sumOdd+=a[i];
   }
}
return Math.max(sumEven,sumOdd);

}
```
```
                             f(n)
    Choose the nth element         f(n-1)
    a[n-1] + f(n-2)
1. Base Case
2. State Representation
3. Transition Repurcusion

public int rob(int[] a){
    return robA(a,a.length);
}

public int robA(int[] a, int n ){
      if(n<0){
          return 0;
      }
      int ch  = a[n-1]+robA(a,n-2);
      int dch = robA(a,n-1);
      return Math.max(ch,cdh);
}

               
	          f(3)
	       /       \
	     /           \
	   /               \
         1 + f(2)           f(2) 
	     /    \        /    \
	 1+f(-1)   f(1)  1+f(-1)   f(1)
```      

> **Nothing Exist like Hard Problem but It is combination of small subproblems**

## Aggresive Cow Problem

## Allocate Pages of Book

## Make Bouqut

## Cut the Tree

## [Visualization](https://www.cs.usfca.edu/~galles/visualization/Search.html)


## Find the First Position of a element in a sorted array

## First & last Occurence of an element

## Find the count of number of Target element in sorted array
- Ans = (Last_occ - first_occ)+1

## Search in Rotated Sorted Array


## Recursive Binary Search


## Square Root of a num in Integer 

## K Sum


## Search in Biotonic Array

## Binary Search in Infinite array

## Minimum Difference element in the Sorted array

## LeetCode 74




## Find element in Row wise sorted array

## Coco eating Banana

## Biotonic array Peak elment


