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
	}
}
```

### [JavaHAshMap](https://www.w3schools.com/java/java_hashmap.asp)
