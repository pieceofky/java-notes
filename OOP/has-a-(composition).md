In Java Object-Oriented Programming (OOP), **"has-a"** composition refers to the relationship where one class **contains** another class as a field. This means one object is **composed** of other objects — hence the term _composition_.

### Explanation:

- **"has-a"** is used to model a **composition** or **aggregation** relationship.
    
- It’s different from **"is-a"**, which models inheritance (`extends` keyword in Java).
    
- Composition is often preferred over inheritance for flexibility.

```java
// Class Address
public class Address {
    String city;
    String state;

    public Address(String city, String state) {
        this.city = city;
        this.state = state;
    }
}

// Class Employee has-a Address
public class Employee {
    String name;
    Address address; // Composition - "has-a" relationship

    public Employee(String name, Address address) {
        this.name = name;
        this.address = address;
    }

    public void display() {
        System.out.println(name + " lives in " + address.city + ", " + address.state);
    }
}

// Main
public class Main {
    public static void main(String[] args) {
        Address addr = new Address("San Francisco", "California");
        Employee emp = new Employee("John Doe", addr);
        emp.display();
    }
}
```

### Key Points:

- `Employee` **has-a** `Address`.
    
- Changing the address logic won't break the `Employee` class.
    
- Promotes **encapsulation** and **code reuse**.

