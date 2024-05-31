### **Day 5: Advanced OOP Concepts and Review (2 Hours)**

#### **Objective:**
- Discuss %, -, +, / operators
- Pass parameters to functions.
- Camel case for variableNames and methodNames, Start with Capital for class.
- Understand and implement static members in Java.
- Learn the use of getters and setters for encapsulation.
- Organize code using packages.
- Review all concepts covered and solidify understanding through a comprehensive example.

#### **Schedule:**

**First Hour:**

1. **Review of Day 4 (10 minutes):**
    - Brief recap of methods, classes, and objects.
    - Quick review of practical examples covered.

2. **Introduction to Static Members (15 minutes):**
    - Explain the concept of static variables and methods.
    - Discuss how static members belong to the class rather than instances.
    - Show examples of using static members.

    **Example:**
    ```java
    public class MathUtils {
        public static final double PI = 3.14159;

        public static double square(double number) {
            return number * number;
        }
    }

    public class Main {
        public static void main(String[] args) {
            System.out.println("Value of PI: " + MathUtils.PI);
            double result = MathUtils.square(5);
            System.out.println("Square of 5: " + result);
        }
    }
    ```

3. **Live Coding Session (10 minutes):**
    - Demonstrate creating and using static variables and methods in a class.
    - Explain when to use static members.

4. **Hands-on Practice (15 minutes):**
    - Students create their own classes with static variables and methods.
    - Examples: Utility classes with static methods for common operations.
    - Assist students as they write and run their programs.

**Second Hour:**

5. **Introduction to Getters and Setters (15 minutes):**
    - Explain the concept of encapsulation in OOP.
    - Discuss the importance of using getters and setters to access and modify private instance variables.
    - Show examples of defining and using getters and setters.

    **Example:**
    ```java
    public class Person {
        private String name;
        private int age;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public int getAge() {
            return age;
        }

        public void setAge(int age) {
            if (age > 0) {
                this.age = age;
            } else {
                System.out.println("Invalid age!");
            }
        }
    }

    public class Main {
        public static void main(String[] args) {
            Person person = new Person();
            person.setName("John");
            person.setAge(25);

            System.out.println("Name: " + person.getName());
            System.out.println("Age: " + person.getAge());
        }
    }
    ```

6. **Live Coding Session (10 minutes):**
    - Demonstrate creating a class with private variables and using getters and setters to access them.
    - Explain how getters and setters help in data validation and encapsulation.

7. **Hands-on Practice (15 minutes):**
    - Students create their own classes with private variables and define getters and setters.
    - Examples: Student class with attributes like name, age, and grade.
    - Assist students as they write and run their programs.

8. **Introduction to Packages (10 minutes):**
    - Explain the concept of packages in Java.
    - Discuss how packages help organize code and prevent naming conflicts.
    - Show how to create and use packages in Java.

    **Example:**
    ```java
    // File: src/com/example/utils/Calculator.java
    package com.example.utils;

    public class Calculator {
        public int add(int a, int b) {
            return a + b;
        }
    }

    // File: src/com/example/app/Main.java
    package com.example.app;

    import com.example.utils.Calculator;

    public class Main {
        public static void main(String[] args) {
            Calculator calculator = new Calculator();
            int result = calculator.add(5, 3);
            System.out.println("Result: " + result);
        }
    }
    ```

9. **Real-World Example: Library Management System (20 minutes):**
    - Create a simple library management system using static members, getters, setters, and packages.

    **Example Program:**
    ```java
    // File: src/com/library/Book.java
    package com.library;

    public class Book {
        private String title;
        private String author;
        private boolean isAvailable;

        public Book(String title, String author) {
            this.title = title;
            this.author = author;
            this.isAvailable = true;
        }

        public String getTitle() {
            return title;
        }

        public String getAuthor() {
            return author;
        }

        public boolean isAvailable() {
            return isAvailable;
        }

        public void setAvailable(boolean available) {
            isAvailable = available;
        }
    }

    // File: src/com/library/Library.java
    package com.library;

    public class Library {
        private static int totalBooks = 0;

        public static void addBook(Book book) {
            totalBooks++;
            System.out.println("Added book: " + book.getTitle());
        }

        public static void issueBook(Book book) {
            if (book.isAvailable()) {
                book.setAvailable(false);
                System.out.println("Issued book: " + book.getTitle());
            } else {
                System.out.println("Book is not available.");
            }
        }

        public static void returnBook(Book book) {
            book.setAvailable(true);
            System.out.println("Returned book: " + book.getTitle());
        }

        public static int getTotalBooks() {
            return totalBooks;
        }
    }

    // File: src/com/library/Main.java
    package com.library;

    public class Main {
        public static void main(String[] args) {
            Book book1 = new Book("The Great Gatsby", "F. Scott Fitzgerald");
            Book book2 = new Book("To Kill a Mockingbird", "Harper Lee");

            Library.addBook(book1);
            Library.addBook(book2);

            System.out.println("Total books in library: " + Library.getTotalBooks());

            Library.issueBook(book1);
            Library.returnBook(book1);

            Library.issueBook(book2);
            Library.issueBook(book2); // Attempt to issue an unavailable book
        }
    }
    ```

    **Explanation:**
    - The `Book` class represents a book with title, author, and availability status.
    - The `Library` class contains static methods to manage the library's books.
    - The main program creates `Book` objects and performs operations like adding, issuing, and returning books.

10. **Q&A Session (10 minutes):**
    - Open the floor for any questions related to the topics covered.
    - Clarify any doubts and provide additional examples if needed.

11. **Recap and Summary (5 minutes):**
    - Review key points covered during the session.
    - Emphasize the importance of static members, getters and setters, and packages in building structured and maintainable programs.

By the end of Day 5, students should feel comfortable with using static members, implementing getters and setters, and organizing code using packages. They will have a solid understanding of advanced OOP concepts and be able to apply them in real-world scenarios.
