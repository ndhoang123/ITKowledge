# CSharp
- Content:
    + [Collections](##Collections): The genetic and non-generic collections.
    + [Boxing and unboxing](##Boxing)
## Collections
- It has two types: **generic** and **non-generic**.
- As Generic, we have: **List**, **Dictionary**, **SortedList**, **Queue**, **Stack**, **Hashset**.

![Generics Collection](./Img/GenericsCollection.png)

- As non-generic, we have: **ArrayList**, **SortedList**, **Stack**, **Queue**, **Hashtable**, **BitArray**.
- In the non-generic, they are stored as object. The compiler have to cast all the object to the specific type.

![Non-Generics Collection](./Img/Non-GenericsCollection.png)

1. **ArrayList**:
- In C#, the ArrayList is a non-generic collection of objects whose size increases dynamically. It is the same as **Array** except that its size increases dynamically.
- An ArrayList can be used to *add* **unknown data** where you don't know the types and the size of data.
2. **List**:
- It is the *generic* version of the **ArrayList** that comes under `System.Collection.Generic` namespace;
- It is **equivalent** of the **ArrayList**, which implements `IList<T>`.
- It contains elements of the specified type, whereas the **ArrayList** can not.
3. **Sorted List**:
- The **Sorted list** are the collection classes that can store key-value pairs that are sorted by the keys based on the associated `IComparer` implementation.
- C# supports generic and non-generic `Sorted list`. It is recommended to use the generic.
- Comes under `System.Collection.Generic` namespace.
- A key must be unique and cannot be null. Otherwise, the value can be duplicate or null.
- A value can be accessed by passing associated key in the indexer.
- It uses less memory than `SortedDictonary`.
4. **Dictionary**
- The `Dictionary<Tkey, TValue>` is a generic collection that stores key-value pairs in no particular order. It is the same as **Sorted List** except they store in no order.
- Implement `IDictionary<Tkey, TValue>` interface.
5. **Hash Table**
- The `Hash table` is a non-generic collection that stores key-value pairs, similar to **Dictionary** except that the hash is non-generic collection.
- It optimizes lookups by **computing the hash code of each key** and stores it in a different bucket internally.
6. **Stack**
- It is both the generic and non-generic collections.
- It works in the **LIFO**.
7. **Queue**
- It is both the generic and non-generic collections.
- It works in the **LIFO**.

Reference: https://www.tutorialsteacher.com/csharp/csharp-queue

## Boxing
1. Boxing:
- Boxing is the process of converting a value type to the type `object` or any interface type implemented by this value. Boxing a value type allocates an object instance on the heap and copies the value into the new object.
- When the CLR boxes a value type, it wraps the value inside a `system.object` and stores it on the managed heap.
```
int i = 123
object o = i // Boxing copies the value of i into object o
```
- The result of this statement is creating an object reference o, on the stack, that references a value of the type int, on the heap. This value is a copy of the value-type value assigned to the variable i.

<div style="text-align:center">
    <img src="./Img/boxing-operation-i-o-variables.gif" />
</div>

- It is also possible to perform the boxing explicitly.

2. **Unboxing**
- Unboxing is an explicit conversion from the type `object` to a `value type` or from an interface type to a value type that implements the interface.
- An unboxing operation consists of:
    + Checking the object instance to make sure that it is a boxed value of the given value type.
    + Copying the value from the instance into the value-type variable.

```
int i = 123;      // a value type
object o = i;     // boxing
int j = (int)o;   // unboxing
```

<div style="text-align:center">
    <img src="./Img/unboxing-conversion-operation.gif" />
</div>

- For the unboxing of value types to `succeed` at **run time**, the item being unboxed **must be a reference** to an object that was **previously created by boxing** *an instance of that value type*. Attempting to unbox **null** causes a **NullReferenceException**. Attempting to unbox a **reference to an incompatible value type** causes an **InvalidCastException**.

Reference: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing