The `final` keyword is used to **restrict modification** in Java. It can be applied to:

1. **Variables** → Value cannot be changed (constant).
    
2. **Methods** → Cannot be overridden.
    
3. **Classes** → Cannot be inherited.
    

---

## **1. `final` Variables (Constants)**

- Once assigned, **value cannot be changed**.
    
- Naming convention: `UPPER_CASE` (for constants).

## **2. `final` Methods (Cannot Be Overridden)**

- Used in inheritance to **prevent method overriding**.
```java
class Parent {
    final void display() {  // Child classes can't override this
        System.out.println("This cannot be overridden.");
    }
}

class Child extends Parent {
    // @Override
    // void display() { ❌ Error: Cannot override final method
    //     System.out.println("Trying to override...");
    // }
}
```

### **When to use `final` methods?**

✔ To **lock method behavior** (e.g., security-critical methods).  
✔ To **prevent accidental modifications** in child classes.


## **3. `final` Classes (Cannot Be Inherited)**

- Prevents a class from being extended.
```java
final class ImmutableString {  // Cannot be inherited
    private String data;
    
    public ImmutableString(String data) {
        this.data = data;
    }
    
    public String getData() {
        return data;
    }
}

// class ExtendedString extends ImmutableString { ❌ Error: Cannot extend final class
// }
```

### **When to use `final` classes?**

✔ For **immutable classes** (e.g., `String`, `Integer` in Java).  
✔ To **prevent inheritance** for security/stability.

## **🔑 Key Takeaways**

|Keyword|Effect|Example Use Cases|
|---|---|---|
|`final` variable|Value cannot change|Constants (`PI`, `MAX_SIZE`)|
|`final` method|Cannot be overridden|Security-critical methods|
|`final` class|Cannot be inherited|Immutable classes (`String`)|

### **Bonus: `final` vs `finally` vs `finalize()`**

- **`final`** → Restricts modification (variables, methods, classes).
    
- **`finally`** → Block in `try-catch` that always executes.
    
- **`finalize()`** → Method called by garbage collector before object deletion (deprecated in Java 9).