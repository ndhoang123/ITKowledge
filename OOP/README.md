# OOP (Object Oriented Programming)
- Content
    + [Features in OOP](#the-features-in-oop)
    + [Overriding and overloading](#overriding-and-overloading)
    + [Access modifiers](#access-modifiers)
    + [Static](#static)
    + [Abstract class and interface](#abstract-class-interface)
    + [Struct](#struct)
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
### **Static class**
- **A static class cannot be instantiated**, that means **the static class** **can not manually** **be created** to **the new instance** by users.

- There is **only one instance**, that is created by system, **will stay in managed heap** until the AppDomain is unloaded.

- All the member **in static class** **must** be **static**.

- Static class is a sealed class so no class could derive from it.

- Because there is no instance variable, you can access the members of a static class by using the `class name itself`.

- A static constructor is only called one time.
### **Static member**
- A **non-static class** can ***contain*** the **static** fields, properties, methods, or events. The static member is callable on a class even when no instance of the class has been created.

- **Static method and properties** ***cannot*** **access non-static fields** and events in their containing types.

- **Static method can be overloaded** but **not overridden**, because they belong to the class, and not to any instance of the class.

- Although a field cannot be declared as static const, a const field is essentially static in its behavior.

- **C# does not support static local variables** (that is, variables that are declared in method scope).

- You could not access static members via an class’ instance but via the class name.

- **Static members** will be **created when the first access**.

## Abstract class, interface
- They are types of abstraction.

### **Abstract class**
- Abstract classes look a lot like interfaces, but they have something more: You can define a behavior for them. It's more about a person saying, "*these classes should look like that, and they have that in common, so fill in the blanks!*".

- It inherits by one class.

- A non-abstract class derived from an abstract class **must include actual implementations of all inherited abstract methods and accessors**.

- Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.

- It can declare and intialize the field and non-abstract method in abstract class.

### **Interface**
- An interface is a contract. Any class or struct that implements that contract must provide an implementation of the members defined in the interface.

- The method in interface do not have the body, and the field cannot declare in the interface.

- Any class or struct that implements that contract must provide an implementation of the members defined in the interface.

- The interface can be implemented by many the derived classes.

- An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.

=> You can think interface as inheritance feature.

## Struct


## Reference
- [OOP explained in depth](https://www.educative.io/blog/object-oriented-programming)
- [Access modifiers in c#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)