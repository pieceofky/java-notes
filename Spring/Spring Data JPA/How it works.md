### **How Spring Data JPA Works:**

1. **Create an Entity Class** (e.g., `User`): This class represents a table in your database.

```java
@Entity
public class User {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private String name;
    private String email;

    // Getters and setters
}
```

**Create a Repository Interface**: Spring Data JPA generates the implementation of the repository interface at runtime. The interface extends `JpaRepository` or `CrudRepository`, and it provides methods like `save()`, `findById()`, `findAll()`, etc.

```java
public interface UserRepository extends JpaRepository<User, Long> {
    
    List<User> findByName(String name); // Custom query based on method name
}
```

- **JpaRepository**: Extends `PagingAndSortingRepository` which in turn extends `CrudRepository`. It provides methods for pagination, sorting, and basic CRUD operations.
    
- You can define **custom queries** based on method names or with `@Query` annotation.