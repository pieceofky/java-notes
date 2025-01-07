In the Spring Framework, **dependency injection (DI)** is a core concept that enables the creation and management of object dependencies. This is fundamental to the **Inversion of Control (IoC)** principle, which decouples object creation and binding from the business logic. Spring provides three primary ways to perform dependency injection:

1. Constructor Injection
2. Setter Injection
3. Field Injection

**Injection Annotations**

In the Spring Framework, dependency injection (DI) is a core concept that enables the creation and management of object dependencies. This is fundamental to the Inversion of Control (IoC) principle, which decouples object creation and binding from the business logic. Spring provides three primary ways to perform dependency injection:
1. Constructor Injection

Dependencies are injected through the class constructor. This is recommended when the dependencies are mandatory and must be provided at object creation.
Example:

@Component
public class ServiceA {
    private final RepositoryA repositoryA;

    // Constructor Injection
    @Autowired
    public ServiceA(RepositoryA repositoryA) {
        this.repositoryA = repositoryA;
    }
}

    Advantages:
        Immutable dependencies (final fields can be used).
        Promotes cleaner code and better testing.
    Configuration:
        Works with both annotation-based (@Autowired) and XML-based configuration.

2. Setter Injection

Dependencies are injected via setter methods. This is useful for optional dependencies or when you want to reconfigure an object after its creation.
Example:

@Component
public class ServiceB {
    private RepositoryB repositoryB;

    // Setter Injection
    @Autowired
    public void setRepositoryB(RepositoryB repositoryB) {
        this.repositoryB = repositoryB;
    }
}

    Advantages:
        Flexibility to change dependencies after object creation.
    Disadvantages:
        May lead to mutable state.
        Requires additional boilerplate code for setters.

3. Field Injection

Dependencies are injected directly into fields using annotations. This is the most concise approach but is generally discouraged in complex systems.
Example:

@Component
public class ServiceC {
    @Autowired
    private RepositoryC repositoryC;
}

    Advantages:
        Minimal boilerplate.
    Disadvantages:
        Reduces testability (e.g., mocking dependencies).
        Makes dependency injection less explicit.


## **Injection Annotations**

### **@Autowired**

- Automatically injects dependencies by type.
- Can be applied to constructors, setters, or fields.
- Can be combined with the `required` attribute (`@Autowired(required = false)`) to make the dependency optional.

### **@Qualifier**

- Used to resolve ambiguity when multiple beans of the same type exist.