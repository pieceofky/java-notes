**A class is a blueprint or template for creating objects.**
### Components of a Class

1. **Fields (Variables)**: These represent the attributes or properties of an object.
2. **Methods**: These define the behavior or actions that can be performed on the objects.
3. **Constructors**: Special methods used to initialize objects.
4. **Access Modifiers**: Keywords like `public`, `private`, `protected` that define the visibility of the class members.

**Syntax of a Class**
```java
class ClassName {
    // Fields
    dataType fieldName;

    // Constructor
    public ClassName() {
        // Initialize fields
    }

    // Methods
    returnType methodName(parameters) {
        // Method body
    }
}
```

**Example 1: Basic Class with Fields and Methods**
```java
public class Car {
    // Fields (Attributes of the car)
    String make;
    String model;
    int year;

    // Constructor to initialize the car object
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Method to display car details
    public void displayDetails() {
        System.out.println("Make: " + make);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }

    // Main method to test the Car class
    public static void main(String[] args) {
        // Creating an object (instance) of the Car class
        Car myCar = new Car("Toyota", "Corolla", 2020);
        
        // Calling a method on the Car object
        myCar.displayDetails();
    }
}
```

**Explanation:
1. **Fields**: The `Car` class has three fields: `make`, `model`, and `year`.
2. **Constructor**: The constructor `Car(String make, String model, int year)` initializes a `Car` object with values for make, model, and year.
3. **Method**: `displayDetails()` prints the details of the car.
4. **Object Creation**: Inside the `main` method, a `Car` object is created using the `new` keyword, and its details are displayed by calling the `displayDetails()` method.

**Example 2: Class with Getter and Setter Methods**
In Java, you often use **getter** and **setter** methods to access and update fields of a class.
```java
public class Person {
    // Fields (Attributes)
    private String name;
    private int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter method for name
    public String getName() {
        return name;
    }

    // Setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for age
    public int getAge() {
        return age;
    }

    // Setter method for age
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Age must be positive.");
        }
    }

    // Method to display person details
    public void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }

    // Main method to test the Person class
    public static void main(String[] args) {
        Person person = new Person("Alice", 25);

        // Using getter methods to access fields
        System.out.println("Initial details:");
        person.displayDetails();

        // Using setter methods to update fields
        person.setAge(30);
        person.setName("Bob");

        // Using getter methods again to display updated details
        System.out.println("\nUpdated details:");
        person.displayDetails();
    }
}
```

**Explanation**
1. **Private Fields**: The `name` and `age` fields are private, meaning they can only be accessed within the `Person` class.
2. **Getter and Setter Methods**: These methods allow controlled access to the fields.
    - `getName()` returns the value of the `name` field.
    - `setName(String name)` allows the `name` to be modified.
    - `getAge()` and `setAge(int age)` do the same for the `age` field.
3. **Main Method**: Creates a `Person` object and demonstrates how to use getter and setter methods to access and modify the object's attributes.

**Example 3: Class with static members**
In Java, static members belong to the class itself rather than to instances (objects) of the class. Static members are shared among all instances of the class.

```java
public class Counter {
    // Static field (shared by all instances)
    static int count = 0;

    // Constructor
    public Counter() {
        count++;  // Increment static count variable every time a new object is created
    }

    // Static method
    public static void displayCount() {
        System.out.println("Count: " + count);
    }

    // Main method to test the static member
    public static void main(String[] args) {
        Counter obj1 = new Counter();
        Counter obj2 = new Counter();
        Counter obj3 = new Counter();

        // Calling static method to display count
        Counter.displayCount();  // Output will be 3
    }
}
```

**Explanation**
- **Static Field**: `count` is a static variable that keeps track of how many objects are created.
- **Static Method**: `displayCount()` is a static method that can be called on the class itself (without creating an object).
- **Main Method**: Three objects of the `Counter` class are created, and each time an object is created, the static `count` variable is incremented. The `displayCount()` method is called to display the total count.

- **Constructors are automatically called when an object is created** using the `new` keyword.
- A **default constructor** is provided if no constructor is explicitly defined in the class.
- A **parameterized constructor** allows initializing an object with specific values at the time of its creation.
- **Constructor overloading** allows multiple constructors with different parameter types to provide flexibility in object initialization.
