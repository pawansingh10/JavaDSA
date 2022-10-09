### Introduction to Hashing
- Please refer Handwritten notes
- Hashmap
```Java
import java.util.*;

public class Main
{
	public static void main(String[] args) {
		System.out.println("HashMap");
		HashMap<String,Integer> hm = new HashMap<>();
		hm.put("MS Dhoni",7);
		hm.put("Virat",18);
		hm.put("KL Rahul",1);
		hm.put("Rohit",45);
		hm.put("Jadeja",8);
		hm.put("Pandya",33);
		hm.put("Bumrah",93);
		System.out.println("MS Dhoni -->"+ hm.get("MS Dhoni"));
		System.out.println("Virat -->"+ hm.get("Virat"));
		System.out.println("Rohit -->"+ hm.get("Rohit"));
		System.out.println("KL Rahul -->"+ hm.get("KL Rahul"));
		System.out.println("Bumrah -->"+ hm.get("Bumrah"));
		
		System.out.println("SKY -->"+ hm.get("SKY"));
		System.out.println("SKY -->"+ hm.getOrDefault("SKY",0));
		System.out.println("SKY -->"+ hm.get("SKY"));
		
		hm.put("SKY",63);
		
		System.out.println(hm);
		System.out.println(hm.size());
	}
}

```

### Creating Freq Map
```java
import java.util.*;

public class Main
{
	public static void main(String[] args) {
		//CREATING FREQENCY ARRAY
		HashMap<Integer,Integer> hm = new HashMap<>();
		
		int[] arr = {1,2,3,2,3,4,3,4,4,4,};
		int n = arr.length;
		
		//One way of creating freq map
		for(int i=0; i<n; i++){
		    if(hm.containsKey(arr[i])){
		        hm.put(arr[i],hm.get(arr[i])+1);
		    }
		    else{
		        hm.put(arr[i],1);
		    }
		}
		System.out.println(hm);
		
		
		//Another way of creating freq map
		for(int i=0; i<n; i++){
		    hm.put(arr[i],hm.getOrDefault(arr[i],0)+1);
		}
		System.out.println(hm);
		
		//Another way
		for(int i=0; i<n; i++){
		   if(hm.get(arr[i])==null){
		       hm.put(arr[i],1);
		   }
		   else{
		       hm.put(arr[i],hm.get(arr[i])+1);
		   }
		}
		System.out.println(hm);
	}
}

```

### Please Visit this Article [Java HashMap](https://www.w3schools.com/java/java_hashmap.asp)

### LeetCode [Valid Anagram](https://leetcode.com/problems/valid-anagram)
```Java
public boolean isAnagram(String s, String t) {
        /*
        1. Create a Freq Map
        2. If the fre of all char are same in both string return true else return false 
        3. So checking count we need to reduce count at the end the freq of all char ==0
        */
        int m =s.length();
        int n =t.length();
        if(m!=n){
            return false;
        }
        
        HashMap<Character,Integer> hm = new HashMap<>();
        
        for(int i=0; i<m; i++){
            char c = s.charAt(i);
            hm.put(c,hm.getOrDefault(c,0)+1);
        }
        
        for(int i=0; i<n; i++){
            char c = t.charAt(i);
            hm.put(c,hm.getOrDefault(c,0)-1);
        }
    
        for(int x : hm.values()){
            if(x!=0){
                return false;
            }
        } 
        return true;
    }
```
### HashMap Traversal | keySet | entrySet
```Java
import java.util.*;

public class Main
{
	public static void main(String[] args) {
		
		HashMap<Integer,Integer> hm = new HashMap<>();
		
		for(int i=1; i<=5; i++){
		    hm.put(i,10*i);
		}
// 		hm.put(-1,-10);
// 		hm.put(-4,-40);
// 		System.out.println(hm);
		
// 		for(int i:hm.keySet()){
// 		    System.out.print(i+"->"+hm.get(i)+" ");
// 		}
// 		System.out.println();
		
		
// 		for(int i : hm.values()){
// 		    System.out.print(i+" ");
// 		}
		
		System.out.println(hm.entrySet());
// 		for(int i : hm.entrySet()){
// 		    System.out.print(i);
// 		}
		
		
		
		for (HashMap.Entry<Integer, Integer> entry :hm.entrySet())
        {
            System.out.println(entry.getKey() + "=" + entry.getValue());
        }
       
	}
}

```

### ASCII - American Standard Code for Information Interchange
- Every char is assigned a number
- ```Java
 public class Main
{
	public static void main(String[] args) {
	    int ch1 ='a';
	    char ch2 = 'a';
		System.out.println(ch1); // 97
		System.out.println(ch2); // a
	}
}```
