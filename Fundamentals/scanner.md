The typical approach to solving programming problems is:

1. Read data from the standard input (System.in);
    
2. Process data to obtain a result;
    
3. Output the result to the standard output (System.out).

## Reading data with a scanner

The simplest method to obtain data from the standard input is using the standard class `Scanner`.
To use this class, you should add the following import statement at the top of your file with the source code.

```java
import java.util.Scanner;
```

After the import, add a class with this construction.

```java
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        sc.close();
    }
}
```

## Reading string values

The `Scanner` class offers various ways to read inputs. If your input is an integer number or a single word, you can use the `next()` method.

```java
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String name = sc.next();

        System.out.println("Hello, " + name + "!");

        sc.close();
    }
}
```

## Reading other data types

Even if you enter a number, both `next()` and `nextLine()` read it as a string. But what if you need to input other types? 

```java
class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        double b = sc.nextDouble();
        boolean c = sc.nextBoolean();

        sc.close();
    }
}
```

Each of these works similarly to `next()`, but instead of reading the input as a string, they scan the input as their corresponding [data types](https://hyperskill.org/learn/step/9055 "In Java, a data type is a category that determines the type of data a variable can hold and the operations that can be performed on it. | Java has two groups of data types: primitive and reference types. Primitive data types are built-in and include eight types, such as int (integer number), float and double (fractional numbers), and boolean (true or false values). Reference types, on the other hand, are used to represent objects, and they are created using the keyword new. When a reference type is created, memory is allocated for the object, and it is called instantiation. Floating-point types, such as float and double, represent numbers that contain an integer part, a fractional part, and their separator, commonly used in fields such as science, statistics, and engineering."). So, while `next()` always returns a string, these methods directly give you the specific type of value you need, making it easier to work with numerical and boolean data.