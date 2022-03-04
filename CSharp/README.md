# CSharp
- Content:
    + [Collections](#collections): The genetic and non-generic collections.
    + [Boxing and unboxing](#boxing)
    + [Mutable and Immutable](#mutable)
    + [Weak Reference](#weak-reference)
    + [Readonly and const](#readonly-and-const)
    + [Reference and value type](#reference-and-value-type)
    + [Reference](#good-reference)

## Collections
- It has two types: **generic** and **non-generic**.
- As Generic, we have: **List**, **Dictionary**, **SortedList**, **Queue**, **Stack**, **Hashset**.

![Generics Collection](https://github.com/ndhoang123/ITKowledge/blob/main/CSharp/Img/GenericsCollection.PNG)

- As non-generic, we have: **ArrayList**, **SortedList**, **Stack**, **Queue**, **Hashtable**, **BitArray**.
- In the non-generic, they are stored as object. The compiler have to cast all the object to the specific type.

![Non-Generics Collection](https://github.com/ndhoang123/ITKowledge/blob/main/CSharp/Img/Non-GenericsCollection.PNG)

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
    <img src="https://github.com/ndhoang123/ITKowledge/blob/main/CSharp/Img/boxing-operation-i-o-variables.gif" />
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
    <img src="https://github.com/ndhoang123/ITKowledge/blob/main/CSharp/Img/unboxing-conversion-operation.gif" />
</div>

- For the unboxing of value types to `succeed` at **run time**, the item being unboxed **must be a reference** to an object that was **previously created by boxing** *an instance of that value type*. Attempting to unbox **null** causes a **NullReferenceException**. Attempting to unbox a **reference to an incompatible value type** causes an **InvalidCastException**.

Reference: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing

## Mutable
1. **Mutable**
- Mutable means that it **can be changed**.
- All the modified value in the object will work in the original memory provided by the system. And no new memory will be created during the operation.
- It is recommended to use in case you want to alter some value in the object and also want to have good performance.
- **StringBuilder** is a mutable.
2. **Immutable**
- In the opposite of Mutable, Immutable means that it **can not be changed**.
- All the modified value in the immutable will be stored in the new object. The original object does not change, because it is unchangeable.
- We are gonna use it in the case we dont consider the other changing easily your object.
- All the unused memory, that was created in the past, will not free immediately, and wait for garbage collection to process. In the case the execution of string more than the GC execution, it causes the worst performance of software.
- **String** is an immutable.
3. **Null and Empty strings**
- Note that you do not use the new operator to create a string object except when initializing the string with an array of chars.
- **An empty string** is an instance of a `System.String` object that contains zero character.
- **A null string** does not refer to an instance of a `System.String` object and `any attempt to call` a `method` on a null string *causes* a **NullReferenceException**. However, you can use null strings in concatenation and comparison operations with other strings.

## Weak Reference
1. Strong reference:
- The Garbage collector cannot collect an object in use by application while the application's code can reach the object. This application is called to have a strong reference to the object.
- Because the object is a **strong reference type**, so **they can not be collected by GC**. Therefore, it may **cause the memory leak**, because the unused object is forced to remain in the memory, which requires you (just as above) to somehow determine when the image is no longer needed in memory and remove it from the cache, so that it becomes eligible for garbage collection 
2. Weak reference:
- A weak reference permits the garbage collector to collect the object while still allowing the application to access the object.
- Another definition, A *weak reference*, simply put, is a reference that **isn't strong enough** to **force an object to remain in memory**. Weak references allow you to leverage the garbage collector's ability to determine reachability for you, so you don't have to do it yourself.
- In C#, weak reference are distiguished by whether they track object resurrection or not. 
    + In C# weak reference do not track resurrection, meaning a weak reference is not updated if an object is resurrected; these are called **short weak references**.
    + Weak references that track resurrection, by using the **finalized** keyword, are called long **weak references**.

## **Readonly and const**
### **Const**
- Once the constant field is assigned, the value of this field is not changed.

=> The const is **constant** in the **compile-time**.
### **Readonly**
- The `readonly` keyword shows that you can assign the value only When the variable is **initialized in the declaration**, in **an instance constructor of the class** that **contains the instance field declaration**, or **in the static constructor of the class** that **contains the static field declaration**.

=> The readonly is **constant** in the **run time**.
#### **Ref readonly return example**
- The `readonly` modifier on a `ref` indicates that the returned reference can't be modified. It uses the `readonly` modifier to indicate that callers can't modify the origin

## Reference and value type
- These are two kinds of types in C#: **value type** and **reference type**
### **Value type**
- It stores in the heap memory.
- A variable of a value type contains an instance of the type.
- Operations on a value-type variable affect only that instance of the value type, stored in the variable.
- With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other.
### **Reference type**
- It stores in stack memory. It has two components: **pointer** stored in the heap, and **stack** stored in the stack.
- Variables of reference types store references to their data, while variables of value type directly contain their data.
- With reference type, two variables can reference the same object, therefore, operations on one object directly affect the object referenced by the other object.

## Good reference:
- [Weak reference by Java](https://web.archive.org/web/20100819115659/http://weblogs.java.net/blog/2006/05/04/understanding-weak-references) (**highly recommend to read!**).
- [Object resurrection](https://en.wikipedia.org/wiki/Object_resurrection)
- [Readonly](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/readonly)