# 3. Variables & Memory

`Variables are memory references`

- memory can be imagined as series of slots in our computer. We can receive and store data from those slots.
- We have a unique address for each slot. 


<center>
<img src="image.png" alt="Example Image" width="300" height="200">
</center>

- certain data may use multiple slots
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
As soon as reference count is 0, memory manager destoys that object and reclaims the memory
Circular references?