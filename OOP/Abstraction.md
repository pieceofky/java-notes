**Abstraction** is a process of hiding the implementation details and showing only functionality to the user.
A principle focused on hiding the implementation details and showing only the essential features of an object. Through the process of abstraction, a programmer hides all but the relevant data about an object in order to reduce complexity and increase efficiency.

**Ways to achieve Abstraction**
Using Abstract Class (0 to 100%)
Using Interface (100%)

### Abstract Class

- An abstract class must be declared with an abstract keyword.
- It can have abstract and non-abstract methods.
- It cannot be instantiated.
- It can have constructors and static methods also.
- It can have final methods which will force the subclass not to change the body of the method.

**Interface**
- support multiple inheritance
	class တစ်ခုကနေပြီး interface တစ်ခုမက အမွေဆက်ခံနိုင်
	interface အချင်းချင်းလည်း တစ်ခုမက အမွေဆက်ခံနိုင်
- connect object from different hierarchy
- polymorphism for many shapes
- static method အမွေမရ
- public static final
- abstract method
- default method

**Ways to create interface instance**
- form child class
- anonymous inner class
- lambda expression (functional style)

**class, abstract class, interface**
class => abstract class (extends)
abstract class => class (extends)
class => interface (implements)
abstract class => interface (implements)
interface => class (error)
class => class or abstract and interface (first extends, then implements)

access => public (default)
non access => abstract (default)
public static final <datatype><identifier> = value;
static method
private method
default method
