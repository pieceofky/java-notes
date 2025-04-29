In JPA, **fetching** defines how related entities are loaded when you query an entity that has relationships (e.g., `@OneToMany`, `@ManyToOne`).

### **1. Lazy Fetching** (Default for `@OneToMany`, `@ManyToMany`)

- **Lazy fetching** means that related entities are **not loaded immediately** when the parent entity is loaded. Instead, they are loaded on-demand when accessed.
    
- This is efficient because it doesn't load unnecessary data upfront.
#### **Example**:

Consider the relationship between `Author` and `Book` (One-to-Many).

```java
@Entity
public class Author {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;

    @OneToMany(fetch = FetchType.LAZY)
    private List<Book> books;

    // Getters and setters
}

@Entity
public class Book {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String title;

    @ManyToOne
    private Author author;

    // Getters and setters
}
```

- **Lazy fetching**: When you fetch an `Author`, the associated `Book` entities are **not** fetched until you access `author.getBooks()` explicitly.

```java
Author author = authorRepository.findById(1L).get();
System.out.println(author.getBooks()); // Books are fetched only when accessed
```

- **Drawback**: If you try to access the related entity outside the transaction, you might get a `LazyInitializationException`.

### **2. Eager Fetching** (Default for `@ManyToOne`, `@OneToOne`)

- **Eager fetching** means that related entities are **loaded immediately** when the parent entity is loaded. This can be inefficient if the related entities are large and not always needed.
#### **Example**:

```java
@Entity
public class Author {
    
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;

    @OneToMany(fetch = FetchType.EAGER)
    private List<Book> books;

    // Getters and setters
}
```

- **Eager fetching**: When you fetch an `Author`, all their `Book` entities are **immediately** loaded, even if you don’t need them right away.

```java
Author author = authorRepository.findById(1L).get();
System.out.println(author.getBooks()); // Books are fetched immediately
```

- **Drawback**: This can lead to performance problems (e.g., fetching too much data) if you don't need all the related entities.

### **Summary**:

- **Lazy fetching**: Related entities are loaded only when accessed. It's more efficient in terms of initial database queries but can lead to `LazyInitializationException` if accessed outside the transaction.
    
- **Eager fetching**: Related entities are loaded immediately, which can be inefficient if the related entities are large and not always required.

---

### **Choosing Between Lazy and Eager**:

- **Lazy**: Best for performance when related entities are not always required (e.g., a list of books for an author may not be needed every time you fetch the author).
    
- **Eager**: Use when you always need the related entities (e.g., a `User` always needs their `Profile`).