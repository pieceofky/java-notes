### **What is Encapsulation?**

Encapsulation is an **OOP principle** that:

- **Bundles data (fields) and methods (behavior) inside a class**
    
- **Restricts direct access to data** by making fields `private`
    
- **Provides controlled access** via public `getters` and `setters`
    

### **Why Use Encapsulation?**

✔ **Data Protection** – Prevents unauthorized modifications  
✔ **Control Access** – Validations can be added in setters  
✔ **Flexibility** – Internal logic can change without breaking other code  
✔ **Maintainability** – Easier to debug and modify

### **How to Implement Encapsulation?**

1. **Make fields `private`** → Hide data from outside the class
    
2. **Provide public `getters` (accessors)** → Read data
    
3. **Provide public `setters` (mutators)** → Modify data (with checks if needed)
    

### **Example**

```java
public class Person {
    private String name;  // Private field
    private int age;

    // Getter (accessor) for name
    public String getName() {
        return name;
    }

    // Setter (mutator) for name
    public void setName(String name) {
        if (name != null && !name.isEmpty()) {  // Validation
            this.name = name;
        }
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age (with validation)
    public void setAge(int age) {
        if (age >= 0) {  // Prevent negative age
            this.age = age;
        }
    }
}
```

### **Key Takeaways**

🔹 **Encapsulation = Data Hiding + Controlled Access**  
🔹 **Private fields + Public getters/setters = Proper encapsulation**  
🔹 **Prevents invalid data** (e.g., negative age)  
🔹 **Makes code more secure and maintainable**

### **When to Use?**

✅ Always, unless you have a **specific reason** to expose fields directly.  
✅ Especially useful when you need **data validation** or **read-only fields** (omit setter).

