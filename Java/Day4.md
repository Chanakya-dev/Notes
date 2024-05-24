### **Day 4: Methods and Basic Object-Oriented Programming (OOP) (2 Hours)**

#### **Objective:**
- Understand and implement methods in Java.
- Learn the basics of Object-Oriented Programming (OOP), including classes and objects.
- Use constructors to initialize objects.

#### **Schedule:**

**First Hour:**

1. **Review of Day 3 (10 minutes):**
    - Brief recap of loops and nested loops.
    - Quick review of practical examples covered.

2. **Introduction to Methods (15 minutes):**
    - Explain the purpose and benefits of using methods.
    - Discuss method definition, parameters, and return types.
    - Show how to call methods from the main program.

    **Example:**
    ```java
    public class Main {
        public static void main(String[] args) {
            greet("Alice");
            int result = add(5, 3);
            System.out.println("Result: " + result);
        }

        public static void greet(String name) {
            System.out.println("Hello, " + name + "!");
        }

        public static int add(int a, int b) {
            return a + b;
        }
    }
    ```

3. **Live Coding Session (15 minutes):**
    - Demonstrate writing methods with and without return values.
    - Show how to pass arguments to methods and return results.

4. **Hands-on Practice (20 minutes):**
    - Students write their own methods to perform simple tasks.
    - Examples: Method to calculate the area of a rectangle, method to check if a number is even or odd.
    - Assist students as they write and run their programs.

**Second Hour:**

5. **Introduction to Classes and Objects (15 minutes):**
    - Explain the concept of classes and objects in OOP.
    - Discuss the difference between classes (blueprints) and objects (instances).
    - Show how to define a class and create objects.

    **Example:**
    ```java
    public class Person {
        String name;
        int age;

        void introduce() {
            System.out.println("My name is " + name + " and I am " + age + " years old.");
        }
    }

    public class Main {
        public static void main(String[] args) {
            Person person1 = new Person();
            person1.name = "John";
            person1.age = 25;
            person1.introduce();

            Person person2 = new Person();
            person2.name = "Jane";
            person2.age = 30;
            person2.introduce();
        }
    }
    ```

6. **Real-World Example: Bank Account Management (20 minutes):**
    - Create a `BankAccount` class with attributes like `accountNumber`, `balance`, and methods for deposit, withdrawal, and checking balance.

    **Example Program:**
    ```java
    public class BankAccount {
        String accountNumber;
        double balance;

        // Constructor to initialize account details
        public BankAccount(String accountNumber, double initialBalance) {
            this.accountNumber = accountNumber;
            this.balance = initialBalance;
        }

        // Method to deposit money
        void deposit(double amount) {
            if (amount > 0) {
                balance += amount;
                System.out.println("Deposited: " + amount);
            } else {
                System.out.println("Invalid deposit amount.");
            }
        }

        // Method to withdraw money
        void withdraw(double amount) {
            if (amount > 0 && amount <= balance) {
                balance -= amount;
                System.out.println("Withdrawn: " + amount);
            } else {
                System.out.println("Invalid withdrawal amount or insufficient balance.");
            }
        }

        // Method to check balance
        void checkBalance() {
            System.out.println("Current balance: " + balance);
        }
    }

    public class Main {
        public static void main(String[] args) {
            // Creating a BankAccount object
            BankAccount account = new BankAccount("123456789", 1000.0);

            // Performing operations on the account
            account.checkBalance();
            account.deposit(500);
            account.withdraw(200);
            account.checkBalance();
        }
    }
    ```

    **Explanation:**
    - The `BankAccount` class represents a bank account with an account number and balance.
    - The constructor initializes the account details.
    - Methods `deposit`, `withdraw`, and `checkBalance` manage the account's operations.
    - The main program creates a `BankAccount` object and performs operations on it.

7. **Hands-on Practice (20 minutes):**
    - Students create their own classes and objects based on real-world scenarios.
    - Examples: Creating a `Car` class with attributes like `make`, `model`, and methods for `startEngine` and `stopEngine`.
    - Assist students as they write and run their programs.

8. **Q&A Session (10 minutes):**
    - Open the floor for any questions related to the topics covered.
    - Clarify any doubts and provide additional examples if needed.

9. **Recap and Summary (5 minutes):**
    - Review key points covered during the session.
    - Emphasize the importance of methods and OOP principles in building modular and maintainable programs.

### **Detailed Examples and Explanations**

#### **Example 1: Method to Calculate Area of a Rectangle**

**Scenario:**
- Create a method that takes the length and width of a rectangle as parameters and returns the area.

**Code:**
```java
public class Main {
    public static void main(String[] args) {
        double length = 5.0;
        double width = 3.0;
        double area = calculateArea(length, width);
        System.out.println("Area of the rectangle: " + area);
    }

    public static double calculateArea(double length, double width) {
        return length * width;
    }
}
```

**Explanation:**
- The `calculateArea` method takes `length` and `width` as parameters and returns the area.
- The main program calls this method and prints the result.

#### **Example 2: Car Class with Methods**

**Scenario:**
- Create a `Car` class with attributes like `make` and `model`, and methods to start and stop the engine.

**Code:**
```java
public class Car {
    String make;
    String model;

    // Method to start the engine
    void startEngine() {
        System.out.println(make + " " + model + " engine started.");
    }

    // Method to stop the engine
    void stopEngine() {
        System.out.println(make + " " + model + " engine stopped.");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car1 = new Car();
        car1.make = "Toyota";
        car1.model = "Camry";
        car1.startEngine();
        car1.stopEngine();

        Car car2 = new Car();
        car2.make = "Honda";
        car2.model = "Civic";
        car2.startEngine();
        car2.stopEngine();
    }
}
```

**Explanation:**
- The `Car` class represents a car with `make` and `model` attributes.
- Methods `startEngine` and `stopEngine` perform actions related to the car.
- The main program creates `Car` objects and calls their methods.

#### **Example 3: Bank Account Management**

**Scenario:**
- Create a `BankAccount` class with methods to deposit, withdraw, and check balance.

**Code:**
```java
public class BankAccount {
    String accountNumber;
    double balance;

    // Constructor to initialize account details
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // Method to deposit money
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }

    // Method to withdraw money
    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        } else {
            System.out.println("Invalid withdrawal amount or insufficient balance.");
        }
    }

    // Method to check balance
    void checkBalance() {
        System.out.println("Current balance: " + balance);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a BankAccount object
        BankAccount account = new BankAccount("123456789", 1000.0);

        // Performing operations on the account
        account.checkBalance();
        account.deposit(500);
        account.withdraw(200);
        account.checkBalance();
    }
}
```

**Explanation:**
- The `BankAccount` class represents a bank account with an account number and balance.
- The constructor initializes the account details.
- Methods `deposit`, `withdraw`, and `checkBalance` manage the account's operations.
- The main program creates a `BankAccount` object and performs operations on it.

By the end of Day 4, students should feel comfortable with defining and using methods, creating classes and objects, and applying basic OOP principles to real-world scenarios.
