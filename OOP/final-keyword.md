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

### **When to use `final` methods?**

✔ To **lock method behavior** (e.g., security-critical methods).  
✔ To **prevent accidental modifications** in child classes.

---

## **3. `final` Classes (Cannot Be Inherited)**

- Prevents a class from being extended.

### **When to use `final` classes?**

✔ For **immutable classes** (e.g., `String`, `Integer` in Java).  
✔ To **prevent inheritance** for security/stability.