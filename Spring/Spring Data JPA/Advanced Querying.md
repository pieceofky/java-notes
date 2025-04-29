- **Custom Queries**: You can define custom JPQL or SQL queries using `@Query`.

```java
public interface UserRepository extends JpaRepository<User, Long> {
    
    @Query("SELECT u FROM User u WHERE u.email = ?1")
    User findByEmail(String email);
}
```
This JPQL query fetches a `User` by email.

- **Native SQL Queries**: You can also use native SQL queries with `@Query(nativeQuery = true)`.

```java
@Query(value = "SELECT * FROM user WHERE email = ?1", nativeQuery = true)
User findByEmailNative(String email);
```

- **Pagination**
Spring Data provides built-in support for pagination using `PageRequest`. This allows you to fetch only a portion of the dataset, which is useful for large databases.

```java
public Page<User> getUsersPaginated(int page, int size) {
    Pageable pageable = PageRequest.of(page, size); // Define page and size
    return userRepository.findAll(pageable); // Returns paginated data
}
```
- **`PageRequest.of(page, size)`**: Creates a pagination request.
- **`findAll(pageable)`**: Returns a page of results.

- **Sorting**
You can also add sorting to your queries using the `Sort` object.

```java
public List<User> getUsersSortedByName() {
    return userRepository.findAll(Sort.by(Sort.Order.asc("name"))); // Ascending order by name
}
```
- `Sort.Order.asc("name")` sorts the result by the `name` field in ascending order.

### **Recap:**

- **Custom queries**: Use `@Query` for more control over SQL or JPQL.
    
- **Pagination**: Use `PageRequest` to fetch data in pages.
    
- **Sorting**: Use `Sort` to sort data by fields in ascending/descending order.
