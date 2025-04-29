**numbers, strings, characters (int, String, char)**

- To use literals, usually you need to store them somewhere. 
- They are stored in [variables](https://hyperskill.org/learn/step/3522 "In Java, a variable is a named storage location that is used to store a value of a specific type. | It is declared with a specific data type, which determines the kind of value that can be stored in it. Every variable has a unique name, also known as an identifier, which is used to access its value. Variables can be declared and initialized in a single statement, and their value can be accessed and modified using the name. It's important to note that variables can be changed, meaning you can assign a new value to a variable without having to declare it again."), which you can think of as containers designed to hold a specific type of data.
- Variables can only store matching data.

**Integer numbers**
```java
int numApples = 1000;

int numPackedApples = 1_000_000;
```

**Characters**
- character literals can only contain a single character
```java
char charOne = '1'
int numOne = 1
```

**Strings**
```java
char singleQuoted = 'A'
String doubleQuoted = "A"
```

**printing literals using variables**
To assign a literal to a variable, you first declare the variable with its type and then initialize with a literal value.

```java
public class Main {
	public static void main(String[] args) {
		int number = 9;
		String greeting = "Hello";

		System.out.println(number);
		System.out.println(greeting);
	}
}
```

## Concatenating data

In practice, you may need to concatenate strings or other literals inside `System.out.println` into a single output. This can be achieved by simply placing them adjacent to each other and use the + operator to join them.

```java
public class Main {
	public static void main(String[] args) {
		String name = "Jonny";
		int age = 53;
		
		System.out.println("Hello" + name + "!");
		System.out.println("You said you are" + age + "years old.");
	}
}
```

