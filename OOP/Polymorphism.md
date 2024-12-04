Polymorphism allows objects of different classes to be treated as objects of a common superclass. The most common types of polymorphism are:

1. **Compile-time Polymorphism (Method Overloading)**
2. **Runtime Polymorphism (Method Overriding)**

### Key Points of Polymorphism

1. **Flexibility and Reusability:** Polymorphism allows for flexibility in coding, enabling one interface to represent multiple behaviors.
2. **Two Types:**
    - **Method Overloading (Compile-time Polymorphism):** Same method name with different parameters.
    - **Method Overriding (Runtime Polymorphism):** Same method signature in both parent and child class but with different implementations.
3. **Dynamic Method Dispatch:** In the case of method overriding, Java uses dynamic method dispatch to decide at runtime which method to call based on the object's actual class.

**Method Overloading**
```java
class Calculator {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }
    
    // Method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }
    
    // Method to add two doubles
    public double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        
        // Calls the method with two integers
        System.out.println(calc.add(10, 20)); // Output: 30
        
        // Calls the method with three integers
        System.out.println(calc.add(10, 20, 30)); // Output: 60
        
        // Calls the method with two doubles
        System.out.println(calc.add(10.5, 20.3)); // Output: 30.8
    }
}
```

**Explanation:**
- The `add` method is overloaded with different parameters (two integers, three integers, and two doubles). This is an example of **compile-time polymorphism** where the method to be executed is determined at compile time based on the method signature.

**Method Overriding**
```java
class Animal {
    // Parent class method
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    // Overriding the sound() method in the child class
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    // Overriding the sound() method in the child class
    @Override
    public void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating objects of Animal, Dog, and Cat
        Animal animal = new Animal();
        Animal dog = new Dog();
        Animal cat = new Cat();
        
        // Demonstrating runtime polymorphism (dynamic method dispatch)
        animal.sound(); // Output: Animal makes a sound
        dog.sound();    // Output: Dog barks
        cat.sound();    // Output: Cat meows
    }
}
```

**Explanation:**
- Here, the `sound()` method is overridden in the `Dog` and `Cat` classes. At runtime, Java decides which method to invoke based on the actual object type (not the reference type).
- This is **runtime polymorphism** (or dynamic method dispatch). Even though the reference type is `Animal`, the actual method that gets executed depends on the object type (`Dog` or `Cat`).

### Key Takeaways:

- **Overloading**: Same method name, but different parameter lists (number/type of parameters). Resolved at compile time.
- **Overriding**: Same method signature in both parent and subclass. Resolved at runtime.
- Polymorphism helps in **code reusability** and **maintainability** by allowing us to use a common interface to handle different types of objects in a consistent way.