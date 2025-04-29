JDBC (Java Database Connectivity) is an API in Java that enables Java applications to interact with relational databases. It provides a standard interface for connecting to, querying, and updating databases. Using JDBC, you can perform operations like executing SQL queries, retrieving results, and managing database connections.

### Key Concepts of JDBC

1. **JDBC Drivers**: These are specific implementations for different database vendors (e.g., MySQL, Oracle, PostgreSQL). A JDBC driver acts as a bridge between the Java application and the database.
    
2. **Connection**: This represents a connection to a database. To interact with a database, you first need to establish a connection using the `DriverManager` or `DataSource` classes.
    
3. **Statement**: This is used to send SQL queries to the database. There are different types of statements:
    - `Statement`: Used for simple SQL queries.
    - `PreparedStatement`: Used for precompiled SQL queries with placeholders, and it can help avoid SQL injection attacks.
    - `CallableStatement`: Used for calling stored procedures.
    
1. **ResultSet**: This represents the result of a query. It's an object that allows you to iterate over the rows of data returned from the database.
    
5. **SQLException**: This is the exception class that is thrown when there are database-related errors.

### Basic Steps for Using JDBC

1. **Load the JDBC Driver**  
    Depending on the database you are using, you load the appropriate JDBC driver class:
```java
Class.forName("com.mysql.cj.jdbc.Driver"); // For MySQL
```

2. **Establish a Connection**  
	Use the `DriverManager.getConnection()` method to create a connection object:
```java
Connection connection = DriverManager.getConnection( "jdbc:mysql://localhost:3306/mydatabase", "username", "password");
```

3. **Create a Statement**  
	Create a `Statement`, `PreparedStatement`, or `CallableStatement` to execute SQL queries.
```java
Statement stmt = connection.createStatement();
```

4. **Execute a Query**  
	Use the `executeQuery()` method for SELECT queries, or `executeUpdate()` for INSERT, UPDATE, DELETE queries.
```java
ResultSet rs = stmt.executeQuery("SELECT * FROM users");
```

5. **Process the ResultSet**  
	Iterate over the `ResultSet` object to retrieve the data.
```java
while (rs.next()) {
    int id = rs.getInt("id");
    String name = rs.getString("name");
    System.out.println(id + ": " + name);
}
```

6. **Close the Connection**  
	It's important to close the `ResultSet`, `Statement`, and `Connection` objects when you're done to free up database resources.
```java
rs.close();
stmt.close();
connection.close();
```

**Example Code**
```java
import java.sql.*;

public class JdbcExample {
    public static void main(String[] args) {
        // Database URL, username, and password
        String url = "jdbc:mysql://localhost:3306/mydatabase";
        String username = "root";
        String password = "password";

        // Initialize the connection and statement
        try (Connection connection = DriverManager.getConnection(url, username, password);
             Statement stmt = connection.createStatement()) {

            // Query to fetch data
            String query = "SELECT * FROM users";
            ResultSet rs = stmt.executeQuery(query);

            // Process the result set
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                System.out.println("ID: " + id + ", Name: " + name);
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

### Types of JDBC Drivers

1. **Type-1 Driver (JDBC-ODBC Bridge Driver)**: Uses ODBC to connect to the database. It's mostly deprecated.
2. **Type-2 Driver (Native-API Driver)**: Uses database-specific client libraries.
3. **Type-3 Driver (Network Protocol Driver)**: Uses a middleware server that translates JDBC calls into database-specific protocols.
4. **Type-4 Driver (Thin Driver)**: Directly communicates with the database using its native protocol. This is the most common and efficient driver.

### Common JDBC Operations

**Insert Data**
```java
String insertSQL = "INSERT INTO users (name, email) VALUES (?, ?)";
try (PreparedStatement pstmt = connection.prepareStatement(insertSQL)) {
    pstmt.setString(1, "John Doe");
    pstmt.setString(2, "john@example.com");
    pstmt.executeUpdate();
}
```

**Update Data**
```java
String updateSQL = "UPDATE users SET email = ? WHERE name = ?";
try (PreparedStatement pstmt = connection.prepareStatement(updateSQL)) {
    pstmt.setString(1, "newemail@example.com");
    pstmt.setString(2, "John Doe");
    pstmt.executeUpdate();
}
```

**Delete Data**
```java
String deleteSQL = "DELETE FROM users WHERE name = ?";
try (PreparedStatement pstmt = connection.prepareStatement(deleteSQL)) {
    pstmt.setString(1, "John Doe");
    pstmt.executeUpdate();
}
```

### Best Practices

- Always use `PreparedStatement` instead of `Statement` to avoid SQL injection.
- Use connection pooling libraries (like HikariCP or Apache Commons DBCP) for efficient database connection management in production.
- Handle exceptions properly, especially `SQLException`, and make sure resources are closed to prevent memory leaks.