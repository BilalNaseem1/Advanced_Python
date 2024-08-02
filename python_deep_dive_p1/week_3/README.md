# 3. Variables & Memory

`Variables are memory references`

- Memory can be imagined as series of slots in our computer. We can receive and store data from those slots.
- We have a unique address for each slot. 


<center>
<img src="image.png" alt="Example Image" width="300" height="200">
</center>

- Certain data may use multiple slots
- What is important to us is that where the object starts in memory
- This sequence of slots are called `Heap`. Storing and retreiving data from a heap is done by Python memory manager.

---
- Running `my_val = 10`, creates an object in memory and stores 10 in that object.
- `my_val` is a reference (is an alias) for the starting address of that object.
```python
hex(id(my_val)) # gives address of the variable 

sys.getrefcount(my_var) # gives reference count
```

- `other_var = my_var` means reference of my_var is assigned to other_var - other_var is also pointing to the same object in memory.
- Python memory manager does reference counting for us.

## Garbage Collection
As soon as reference count is 0, memory manager destoys that object and reclaims the memory - `BUT SOMETIMES THAT DOES NOT WORK!`

- Below my_var points to object A, which has an instance var_1 which points to object B.
- Deleting my_var, reference count of object A goes to 0.
- In this case, since reference count of object A =0 it will get destroyed, consequently reference count of object B = 0 hence it will also get destroyed.
- Removing my_var causes, Python memory manager will get rid of object A and B.

<center>
<img src="image-1.png" alt="Example Image" width="400" height="100">
</center>

In case if object B also has an instance variable `val_2` which points back to object A - This case is known as `Circular Reference`.
- In this case even if we delete my_var reference, reference count of object A will be 1 (was 2 previously).
- If we leave like this, we will have a memory leak - memory manager cannot clean this
- This can only be cleaned by Garbage collection - by default garbage collection is turned on.
- Garbage collector can be controlled programmatically using the `gc` module.

<center>
<img src="image-2.png" alt="Example Image" width="450" height="200">
</center>

## Dynamic vs Static Typing
### Static typing
- Programming languages which require a data type for a variable, are called statically typed languages.
- The data type is also associated with the variable, and the object also ofcourse.
- Java, C++ etc are statically typed

```java
String my_var = 10;

//later if we do this - this WONT work!!
my_var = 10; // will throw an error

// but this will work
my_var = "abc"; 
```
### Dynamic typing
- Python is dynamically typed. `my_var` would only be a reference to a string object.
- my_var does not have type, so it can reference an int later on.

## Object Mutability
- An object stored in a memory address has 2 things
    1. Type
    2. State

- Changing data `inside` the object is called modifying the internal state of the object.............