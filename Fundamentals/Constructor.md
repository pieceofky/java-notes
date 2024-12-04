A **constructor** is a special method used to initialize objects. It is called automatically when an object of a class is created. The primary purpose of a constructor is to set the initial values for the object’s attributes or to perform any setup steps necessary for the object.

### Characteristics of Constructors

1. **Name**: A constructor must have the same name as the class.
2. **No Return Type**: Unlike methods, constructors do not have a return type, not even `void`.
3. **Called Automatically**: When an object is created using the `new` keyword, the constructor is called automatically.
4. **Can be Overloaded**: Java allows constructor overloading, meaning you can define multiple constructors with different parameter lists.

### Types of Constructors in Java

1. **Default Constructor** (No-argument constructor):
    
    - A default constructor is provided by Java if no constructors are defined in the class.
    - It initializes the instance variables to default values (e.g., `0` for integers, `null` for objects, etc.).
    - If a constructor is explicitly defined, Java will **not** provide the default constructor.

**Example:**
```java
class Car {
    String make;
    String model;

    // Default constructor
    Car() {
        make = "Unknown";
        model = "Unknown";
    }
}
```

**Parameterized Constructor**:

- A parameterized constructor allows you to provide initial values for the object’s attributes at the time of creation.
- It takes one or more arguments to initialize the fields of the object with specific values.

**Example**:
```java
class Car {
    String make;
    String model;

    // Parameterized constructor
    Car(String make, String model) {
        this.make = make;
        this.model = model;
    }
}
```

