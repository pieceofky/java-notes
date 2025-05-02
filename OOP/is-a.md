In Java OOP, **"is-a"** represents an **inheritance relationship** where one class is a specialized version of another class. This is implemented using the `extends` keyword for classes and `implements` for interfaces.

---

### Key Concept:

- **"is-a"** = **Inheritance**
    
- A subclass **inherits** the properties and behaviors (methods) of its parent class.
    
- Used to model a hierarchy.

```java
// Superclass
public class Animal {
    public void makeSound() {
        System.out.println("Some generic sound");
    }
}

// Subclass - Dog "is-a" Animal
public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Bark");
    }
}

// Main
public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.makeSound();  // Output: Bark
    }
}
```

### Summary:

- `Dog` **is-a** `Animal`.
    
- It inherits `makeSound()` from `Animal`, but overrides it.
    
- Promotes **code reuse** and **polymorphism**.