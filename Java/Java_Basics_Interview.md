```markdown
# Java Flashcards

## 1. Variables and Data Types

**Q:** How do you declare an integer variable named `age` and assign it the value of 25?  
**A:** `int age = 25;`

**Q:** How do you declare a string variable named `name` and assign it the value of "John"?  
**A:** `String name = "John";`

**Q:** How do you declare a double variable named `score` and assign it the value of 85.5?  
**A:** `double score = 85.5;`

## 2. Basic Input and Output

**Q:** How do you print the string "Hello, World!" to the console?  
**A:** `System.out.println("Hello, World!");`

**Q:** How do you create a `Scanner` object to read user input from the console?  
**A:** `Scanner scanner = new Scanner(System.in);`

**Q:** How do you read a line of text entered by the user and store it in the `input` variable?  
**A:** `String input = scanner.nextLine();`

## 3. Conditional Statements

**Q:** What is the syntax for an if-else statement in Java?  
**A:** `if (condition) { ... } else { ... }`

**Q:** What is the syntax for a switch statement in Java?  
**A:** `switch (variable) { case value1: ... break; case value2: ... break; default: ... }`

## 4. Loops

**Q:** How do you write a for loop that executes a code block repeatedly, with the variable `i` incrementing from 0 to 4?  
**A:** `for (int i = 0; i < 5; i++) { ... }`

**Q:** How do you write a while loop that executes a code block repeatedly as long as a condition remains true?  
**A:** `while (condition) { ... }`

## 5. Methods

**Q:** How do you define a method named `myMethod` with no return value and no parameters?  
**A:** `public static void myMethod() { ... }`

**Q:** How do you define a method named `sum` that takes two integer parameters, adds them, and returns the result?  
**A:** `public static int sum(int a, int b) { return a + b; }`

## 6. Classes and Objects

**Q:** How do you define a class named `MyClass`?  
**A:** `public class MyClass { ... }`

**Q:** How do you create an object of the `MyClass` class and assign it to the variable `obj`?  
**A:** `MyClass obj = new MyClass();`

**Q:** How do you define a method named `myMethod` inside a class, which can be called on an object of that class?  
**A:** `public void myMethod() { ... }`

## 7. Arrays

**Q:** How do you declare an integer array named `numbers` and initialize it with the values 1, 2, 3, 4, and 5?  
**A:** `int[] numbers = {1, 2, 3, 4, 5};`

**Q:** How do you declare a string array named `names` with a length of 3?  
**A:** `String[] names = new String[3];`

## 8. Exception Handling

**Q:** What is the syntax for a try-catch block in Java?  
**A:** `try { ... } catch (ExceptionType e) { ... }`

**Q:** How do you throw an `IllegalArgumentException` with the specified error message?  
**A:** `throw new IllegalArgumentException("Invalid input");`

## 9. Simple Java Program

**Q:** Write a simple Java program to print "Hello, World!".  
**A:** 
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**Q:** What is the entry point of a Java program?  
**A:** The main method: `public static void main(String[] args)`

## 10. Data Types

**Q:** List all the primitive data types in Java.  
**A:** `byte, short, int, long, float, double, char, boolean.`

**Q:** How do you declare a char variable and assign it the value 'A'?  
**A:** `char letter = 'A';`

**Q:** What is the default value of an int variable?  
**A:** `0.`

**Q:** How do you declare an array of integers in Java?  
**A:** `int[] numbers = new int[10];`

**Q:** How do you declare a string variable and assign it the value "Hello"?  
**A:** `String greeting = "Hello";`

## 11. Variables

**Q:** How do you declare and initialize a boolean variable?  
**A:** `boolean isTrue = true;`

**Q:** What is the difference between an instance variable and a local variable?  
**A:** An instance variable is declared inside a class but outside any method, while a local variable is declared inside a method.

**Q:** How do you declare a constant variable?  
**A:** `final int MAX_VALUE = 100;`

## 12. Operators

**Q:** What is the result of 10 % 3?  
**A:** `1.`

**Q:** How do you perform a bitwise AND operation between two integers?  
**A:** `int result = a & b;`

**Q:** What does the `++` operator do?  
**A:** It increments a variable by 1.

**Q:** How do you compare two variables for equality?  
**A:** Using the `==` operator, e.g., `a == b`.

**Q:** What is the logical OR operator in Java?  
**A:** `||.`

## 13. Control Flow Statements

### Conditional Statements

**Q:** How do you write an if-else statement to check if a number is positive or negative?  
**A:** 
```java
if (number > 0) {
    System.out.println("Positive");
} else {
    System.out.println("Negative");
}
```

**Q:** Write a switch-case statement that prints the day of the week based on an integer value (1 for Monday, 2 for Tuesday, etc.).  
**A:** 
```java
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    // other cases
    default:
        System.out.println("Invalid day");
        break;
}
```

## 14. Loops

**Q:** Write a for loop that prints numbers from 1 to 5.  
**A:** 
```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

**Q:** Write a while loop that prints numbers from 1 to 5.  
**A:** 
```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

**Q:** Write a do-while loop that prints numbers from 1 to 5.  
**A:** 
```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

**Q:** How do you use an enhanced for loop to iterate over an array of integers?  
**A:** 
```java
int[] numbers = {1, 2, 3, 4, 5};
for (int number : numbers) {
    System.out.println(number);
}
```

## 15. Branching Statements

**Q:** Write a for loop that exits when the variable equals 3.  
**A:** 
```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        break;
    }
    System.out.println(i);
}
```

**Q:** Write a for loop that skips printing the number 3.  
**A:** 
```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }
    System.out.println(i);
}
```

**Q:** What is the purpose of the return statement in a method?  
**A:** It exits the method and optionally returns a value.

## 16. Object-Oriented Programming (OOP) Concepts

### Classes and Objects

**Q:** How do you define a class named Person with fields name and age?  
**A:** 
```java
public class Person {
    String name;
    int age;
}
```

**Q:** How do you create an object of the Person class?  
**A:** `Person person = new Person();`

**Q:** Write a constructor for the Person class that initializes the name and age fields.  
**A:** 
```java
public Person(String name, int age) {
    this.name = name;
    this.age = age;
}
```

### Methods

**Q:** How do you define a method that returns the square of an integer?  
**A:** 
```java
public int square(int number) {
    return number * number;
}
```

**Q:** Write a method that takes a String and prints it in uppercase.  
**A:** 
```java
public void print

UpperCase(String str) {
    System.out.println(str.toUpperCase());
}
```

**Q:** How do you call a method named greet on an object person of class Person?  
**A:** `person.greet();`

**Q:** Write a method that takes two integers and returns their sum.  
**A:** 
```java
public int add(int a, int b) {
    return a + b;
}
```

**Q:** What is method overloading?  
**A:** Method overloading is defining multiple methods with the same name but different parameters.

**Q:** Give an example of method overloading.  
**A:** 
```java
public int add(int a, int b) {
    return a + b;
}

public double add(double a, double b) {
    return a + b;
}
```

**Q:** What is method overriding?  
**A:** Method overriding is redefining a method in a subclass that already exists in the superclass with the same signature.

**Q:** How do you override a method in Java?  
**A:** 
```java
@Override
public void methodName() {
    // implementation
}
```

**Q:** What is a static method?  
**A:** A static method belongs to the class rather than any instance and can be called without creating an object of the class.

**Q:** How do you define a static method?  
**A:** 
```java
public static void myStaticMethod() {
    // code
}
```

**Q:** Can a static method access instance variables?  
**A:** No, static methods cannot access instance variables directly.
```
