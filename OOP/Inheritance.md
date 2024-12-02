When you inherit from an existing class, you can reuse methods and fields of the parent class. Moreover, you can add new methods and fields in your current class also.

Inheritance represents the **IS-A relationship** which is also known as a _parent-child_ relationship.

Programmer is a Person
Person => Parent Class (Super Class, Base)
Programmer => Child Class (Sub Class, Derived)

### Terms used in Inheritance

- **Class:** A class is a group of objects which have common properties. It is a template or blueprint from which objects are created.
- **Sub Class/Child Class:** Subclass is a class which inherits the other class. It is also called a derived class, extended class, or child class.
- **Super Class/Parent Class:** Superclass is the class from where a subclass inherits the features. It is also called a base class or a parent class.
- **Reusability:** Reusability is a mechanism which facilitates you to reuse the fields and methods of the existing class when you create a new class. You can use the same fields and methods already defined in the previous class.

**Syntax of Java Inheritance** 

```java
class Subclass-name extends Superclass-name {
// methods and fileds
}

class Car extends Vehicle {
// Car IS-A Vehicle
}
```

Object 
- has no parent (super) class
- has default constructor without argument

parent class default constructor => super(); => first line မှာပဲ ရှိရမယ်

**Things to happen after inheritance**
1. Polymorphism
2. Method Overriding
3. Type Casting

**Rules for Method Overriding**
- parent void => child void
- primitive return type in parent => same primitive type in child
- object return type in parent => so it's and its sub-type in child // covariant return type
- same method name
- same argument list
- same access and widening access from parent

public => protected => default => private
(if protected - then automatically inherited)

intVal = shortVal // implicit cast or upcast
shortVal = (short) intVal // explicit cast or downcast

bigger type can't assign to smaller type => solution is casting

**Overloading**
same method name in same class
different argument list
same return type // optional but recommend
same access // optional but recommend

- overloading can occur without inheritance
- overriding can occur either way

**this() vs super()**
this() is only explicit
super() is both implicit and explicit
this() => for invoking other constructor in the same class
super() => for invoking other constructor in the parent class

**casting class**
need to downcast in order to get child type
object that to pass must be casting type or its sub type
must not be its super type or other class

potential error => ClassCastException
	when: 


concrete class, abstract class => multiple inheritance unavailable