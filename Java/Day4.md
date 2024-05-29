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
    - Students write their own methods for simple tasks.
    - Example tasks: Calculate the area of a rectangle, check if a number is even or odd.
    - Assist students as they write and run their programs.

---

**Second Hour:**

1. **Introduction to Classes and Objects (15 minutes):**
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

2. **Real-World Example: Bank Account Management (20 minutes):**
    - Create a `BankAccount` class with attributes like accountNumber, balance, and methods for deposit, withdrawal, and checking balance.

    **Example:**
    ```java
    public class BankAccount {
        String accountNumber;
        double balance;

        public BankAccount(String accountNumber, double initialBalance) {
            this.accountNumber = accountNumber;
            this.balance = initialBalance;
        }

        void deposit(double amount) {
            if (amount > 0) {
                balance += amount;
                System.out.println("Deposited: " + amount);
            } else {
                System.out.println("Invalid deposit amount.");
            }
        }

        void withdraw(double amount) {
            if (amount > 0 && amount <= balance) {
                balance -= amount;
                System.out.println("Withdrawn: " + amount);
            } else {
                System.out.println("Invalid withdrawal amount or insufficient balance.");
            }
        }

        void checkBalance() {
            System.out.println("Current balance: " + balance);
        }
    }

    public class Main {
        public static void main(String[] args) {
            BankAccount account = new BankAccount("123456789", 1000.0);
            account.checkBalance();
            account.deposit(500);
            account.withdraw(200);
            account.checkBalance();
        }
    }
    ```

3. **Hands-on Practice (20 minutes):**
    - Students create their own classes and objects based on real-world scenarios.
    - Example: Create a `Car` class with attributes like make, model, and methods for startEngine and stopEngine.
    - Assist students as they write and run their programs.

4. **Q&A Session (10 minutes):**
    - Open the floor for questions related to the topics covered.
    - Clarify any doubts and provide additional examples if needed.

5. **Recap and Summary (5 minutes):**
    - Review key points covered during the session.
    - Emphasize the importance of methods and OOP principles in building modular and maintainable programs.

---

**By the end of Day 4, students should feel comfortable with defining and using methods, creating classes and objects, and applying basic OOP principles to real-world scenarios.**
