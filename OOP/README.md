# OOP (Object Oriented Programming)
- Content
    + [Features in OOP](#the-features-in-oop)
    + [Overriding and overloading](#overriding-and-overloading)
    + [Access modifiers](#access-modifiers)
    + [Static](#static)
    + [Reference](#reference)

## The features in OOP
- 4 features in OOP: **Inheritance**, **Abstraction**, **Polymorphism**, **Encapsulation**.
    + **Inheritance**: Allow classes to inherit features of other class.
    + **Encapsulation**: Containing information in an object, exposing only selected information.
    + **Abstraction**: Only exposing high level public methods for accessing an object.
    + **Polymorphism**: Many methods can do the same task.

## Overriding and overloading
- In the OOP, we have two types of polymorphism: **overriding**, **overloading**.
### **Overridding (Runtime polymorphism)**
- In method overriding, *the properties*, having the **same name properties** in *parent class*, *in the child class* can **provide different implemetation with the name**.
### **Overloading (Compile-time polymorphism)**
- In method overloading, *methods or functions in the same class* may **have the same name**, but a **different number of parameters passed into the method call**.

## Access modifiers
- All types and type members have an accessibility level. The accessibility level controls whether they can be used from other code in your assembly or other assemblies.
- Use the following access modifiers to specify the accessibility of a type or member when you declare it:
    + **Public**: The method, attribute or property can be accessed by any code in the `same assembly`, or `the other assembly` that reference it.
    + **Private**: The method, attribute or property can be accessed by the same `class` or `struct`.
    + **Protected**: The method, attribute or property can be accessed by the same `class` or the `inherited class`.
    + **Internal**: The method, attribute or property can be accessed by the `same assembly` but not from the `other assembly`. In the other word, the `internal` type, or member can be accessed from code that is part of the same compilation.
    + **Protected internal**: The method, attribute or property can be accessed by the `same assembly`, or from within a `derived class` in another assembly.
    + **Private protected**: The type or member can be accessed by types derived from the `class` that are declared within its containing assembly.
- **Summary Table**

    | Caller's location | `public` | `protected internal` | `protected`| `internal`| `private protected`| `private`|
    | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
    | Within the class | ✔️️| ✔️️| ✔️| ✔️️| ✔️| ✔️️| ✔️️|
    | Derived class (same assembly) | ✔️| ✔️️| ✔️| ✔️| ✔️| ❌|
    | Non-derived class (same assembly)| ✔️️| ✔️| ❌| ✔️️| ✔️️| ❌|
    | Derived class (different assembly)| ✔️️| ✔️️| ❌| ❌| ❌| ❌|
    | Non-derived class (different assembly)| ✔️️| ❌| ❌| ❌| ❌| ❌|

## Static

## Reference
- [OOP explained in depth](https://www.educative.io/blog/object-oriented-programming)
- [Access modifiers in c#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)