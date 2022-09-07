***
# Hashing
- Hashing is a process or technique of mapping **Keys - values** into hash table by using hash function
- Faster access of element
- Efficiency of mapping depends on Hash Function
- ![image](https://user-images.githubusercontent.com/47448422/188796108-77be309f-19fa-4cb6-8498-bba5c413a4b7.png)

***

***
- Suppose we want to design a system for storing employee records with phone numbers(as keys).
- And we want the following queries to be performed efficiently: 
1. Insert a phone number and corresponding information.
2. Search a phone number and fetch the information.
3. Delete a phone number and related information.

- We can think of using the following data structures to maintain information about different phone numbers. 
1. Array of phone numbers and records.
2. Linked List of phone numbers and records.
3. Balanced binary search tree with phone numbers as keys.
4. Direct Access Table.
***

***
## Basic Operation
- **HashTable** : This operation is used in order to create a new hash table.
- **Delete** : This operation is used in order to delete a particular key-value pair from the hash table.
- **Get** : This operation is used in order to search a key inside the hash table and return the value that is associated with that key.
- **Put** : This operation is used in order to insert a new key-value pair inside the hash table.
- **DeleteHashTable** : This operation is used in order to delete the hash table
***

***
## Hashing Components
1. Hash Table
2. Hash Function
3. A good hash function should have following properties:
i.   Efficiently computable. 
ii.  Should uniformly distribute the keys (Each table position equally likely for each).
iii. Should minimize collisions.
iv.  Should have a low load factor(number of items in table divided by size of the table)
***

***

##  Collision Handling
- Since a hash function gets us a small number for a big key, there is possibility that two keys result in same value.
- The situation where a newly inserted key maps to an already occupied slot in hash table is called collision and must be handled using some collision handling technique
- Following are the ways to handle collisions :-
  - Chaining
  - Open Addressing

## Chaining
- The idea is to make each cell of hash table point to a linked list of records that have same hash function value. 
- Chaining is simple, but requires additional memory outside the table.

## Open Addressing
- In open addressing, all elements are stored in the hash table itself. Each table entry contains either a record or NIL. 
- When searching for an element, we examine the table slots one by one until the desired element is found or it is clear that the element is not in the table.


***
