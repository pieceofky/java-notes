if-else Statement

**It is used to test the condition. It checks Boolean condition: true or false.**
- if statement
- if-else statement
- if-else-if ladder
- nested if statement

**if Statement**
IfExample.java
```java
//Java Program to demonstate the use of if statement.
public class IfExample {
public static void main(String[] args) {
    //defining an 'age' variable
	int age=20;
	//checking the age
	if(age>18){
		System.out.print("Age is greater than 18");
	}
}
}
```

**if-else Statement**
IfElseExample.java
```java
1. //A Java Program to demonstrate the use of if-else statement.  
2. //It is a program of odd and even number.  
3. public class IfElseExample {  
4. public static void main(String[] args) {  
5.     //defining a variable  
6.     int number=13;  
7.     //Check if the number is divisible by 2 or not  
8.     if(number%2==0){  
9.         System.out.println("even number");  
10.     }else{  
11.         System.out.println("odd number");  
12.     }  
13. }  
14. }
```
LeapYearExample.java
```java
1. public class LeapYearExample {    
2. public static void main(String[] args) {    
3.     int year=2020;    
4.     if(((year % 4 ==0) && (year % 100 !=0)) || (year % 400==0)){  
5.         System.out.println("LEAP YEAR");  
6.     }  
7.     else{  
8.         System.out.println("COMMON YEAR");  
9.     }  
10. }    
11. }
```

**if-else-if ladder Statement**
IfElseIfExample.java
```java
1. //Java Program to demonstrate the use of If else-if ladder.  
2. //It is a program of grading system for fail, D grade, C grade, B grade, A grade and A+.  
3. public class IfElseIfExample {  
4. public static void main(String[] args) {  
5.     int marks=65;  

7.     if(marks<50){  
8.         System.out.println("fail");  
9.     }  
10.     else if(marks>=50 && marks<60){  
11.         System.out.println("D grade");  
12.     }  
13.     else if(marks>=60 && marks<70){  
14.         System.out.println("C grade");  
15.     }  
16.     else if(marks>=70 && marks<80){  
17.         System.out.println("B grade");  
18.     }  
19.     else if(marks>=80 && marks<90){  
20.         System.out.println("A grade");  
21.     }else if(marks>=90 && marks<100){  
22.         System.out.println("A+ grade");  
23.     }else{  
24.         System.out.println("Invalid!");  
25.     }  
26. }  
27. }
```

```java
1. public class PositiveNegativeExample {    
2. public static void main(String[] args) {    
3.     int number=-13;    
4.     if(number>0){  
5.     System.out.println("POSITIVE");  
6.     }else if(number<0){  
7.     System.out.println("NEGATIVE");  
8.     }else{  
9.     System.out.println("ZERO");  
10.    }  
11. }    
12. }
```

