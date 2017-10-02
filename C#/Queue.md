---
title: Queue
---
## Queue
- First-In-First-Out
- Queue / Queue< T >
- Implement ICollection, IEnumerable, ICloneable
### Enqueu 
- Add a value
```c#
Queue<int> temp = new Queue<int>();
temp.Enqueue(1);
temp.Enqueue(2);
temp.Enqueue(3);
// 1,2,3

```
### Dequeue
- Return and removed the first element.

```c#
var first = temp.Dequeue();
// first => 1
// temp => 2、3
```

### Peek
- Peek 	 : Return the first element.
```c#
var first = temp.Peek();
// first =>1
// temp => 1、2、3
```

### CopyTo(Array array,int index)
- Array : The array you want to copy Queue to.
- The start copy index of array.
```c#
var array = [4];
array[0] = 0;
temp.CopyTo(array,1);
```
