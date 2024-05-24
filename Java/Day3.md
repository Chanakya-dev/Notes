### **Day 3: Control Flow (Part 2) (2 Hours)**

#### **Objective:**
- Understand and implement loops in Java (`for`, `while`, `do-while`).
- Learn about nested loops and their applications.
- Apply loops to solve real-world problems.

#### **Schedule:**

**First Hour:**

1. **Review of Day 2 (10 minutes):**
    - Brief recap of basic input/output and conditional statements.
    - Quick review of logical operators used in conditions.

2. **Introduction to Loops (15 minutes):**
    - Explain the purpose of loops in programming.
    - Discuss the different types of loops in Java: `for`, `while`, and `do-while`.
    - Show the syntax and structure of each loop with examples.

    **For Loop Example:**
    ```java
    for (int i = 0; i < 5; i++) {
        System.out.println("Count: " + i);
    }
    ```

    **While Loop Example:**
    ```java
    int count = 0;
    while (count < 5) {
        System.out.println("Count: " + count);
        count++;
    }
    ```

    **Do-While Loop Example:**
    ```java
    int count = 0;
    do {
        System.out.println("Count: " + count);
        count++;
    } while (count < 5);
    ```

3. **Live Coding Session (15 minutes):**
    - Demonstrate writing programs using each type of loop.
    - Highlight the differences and appropriate use cases for each loop.

    **Example Program:**
    ```java
    public class Main {
        public static void main(String[] args) {
            // For loop
            for (int i = 0; i < 5; i++) {
                System.out.println("For Loop Count: " + i);
            }

            // While loop
            int count = 0;
            while (count < 5) {
                System.out.println("While Loop Count: " + count);
                count++;
            }

            // Do-while loop
            int doCount = 0;
            do {
                System.out.println("Do-While Loop Count: " + doCount);
                doCount++;
            } while (doCount < 5);
        }
    }
    ```

4. **Hands-on Practice (20 minutes):**
    - Students write their own programs using each type of loop.
    - Encourage students to experiment with different loop conditions and increments.
    - Assist students as they write and run their programs.

**Second Hour:**

5. **Introduction to Nested Loops (15 minutes):**
    - Explain the concept of nested loops.
    - Discuss real-world scenarios where nested loops are useful, such as iterating through a 2D array or creating patterns.

    **Example:**
    ```java
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            System.out.println("i = " + i + ", j = " + j);
        }
    }
    ```

6. **Real-World Example: Multiplication Table (10 minutes):**
    - Show how to use nested loops to generate a multiplication table.

    **Example Program:**
    ```java
    public class Main {
        public static void main(String[] args) {
            for (int i = 1; i <= 10; i++) {
                for (int j = 1; j <= 10; j++) {
                    System.out.print(i * j + "\t");
                }
                System.out.println();
            }
        }
    }
    ```

    **Explanation:**
    - The outer loop iterates through the numbers 1 to 10.
    - The inner loop multiplies the outer loop's current value by values from 1 to 10 and prints the result.
    - The result is a multiplication table from 1 to 10.

7. **Hands-on Practice (20 minutes):**
    - Students create their own programs using nested loops.
    - Assign tasks such as generating different patterns (e.g., triangles, squares) or processing 2D arrays.
    - Assist students as they write and run their programs.

8. **Complex Real-World Example: Simple ATM System (10 minutes):**
    - Demonstrate a simple ATM system using loops and conditionals.
    - Allow users to perform actions such as checking balance, depositing money, and withdrawing money.

    **Example Program:**
    ```java
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            double balance = 1000.0;
            int choice;

            do {
                System.out.println("ATM Menu:");
                System.out.println("1. Check Balance");
                System.out.println("2. Deposit Money");
                System.out.println("3. Withdraw Money");
                System.out.println("4. Exit");
                System.out.print("Choose an option: ");
                choice = scanner.nextInt();

                switch (choice) {
                    case 1:
                        System.out.println("Your balance is $" + balance);
                        break;
                    case 2:
                        System.out.print("Enter deposit amount: ");
                        double deposit = scanner.nextDouble();
                        balance += deposit;
                        System.out.println("Your new balance is $" + balance);
                        break;
                    case 3:
                        System.out.print("Enter withdrawal amount: ");
                        double withdrawal = scanner.nextDouble();
                        if (withdrawal <= balance) {
                            balance -= withdrawal;
                            System.out.println("Your new balance is $" + balance);
                        } else {
                            System.out.println("Insufficient balance.");
                        }
                        break;
                    case 4:
                        System.out.println("Thank you for using the ATM. Goodbye!");
                        break;
                    default:
                        System.out.println("Invalid option. Please try again.");
                }
            } while (choice != 4);
        }
    }
    ```

    **Explanation:**
    - The program uses a `do-while` loop to display an ATM menu repeatedly.
    - It allows the user to check balance, deposit money, withdraw money, or exit the system.
    - It uses a `switch` statement to handle the user's choice and perform the appropriate action.

9. **Q&A Session (10 minutes):**
    - Open the floor for any questions related to the topics covered.
    - Clarify any doubts and provide additional examples if needed.

10. **Recap and Summary (5 minutes):**
    - Review key points covered during the session.
    - Emphasize the importance of loops and nested loops in solving repetitive tasks and real-world problems.

### **Detailed Examples and Explanations**

#### **Example 1: Generating a Multiplication Table**

**Scenario:**
- Create a program that generates and prints a multiplication table from 1 to 10.

**Code:**
```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            for (int j = 1; j <= 10; j++) {
                System.out.print(i * j + "\t");
            }
            System.out.println();
        }
    }
}
```

**Explanation:**
- The outer loop iterates from 1 to 10.
- The inner loop multiplies the outer loop's current value by values from 1 to 10.
- The result is printed in a tabular format to form a multiplication table.

#### **Example 2: ATM System**

**Scenario:**
- Create a simple ATM system that allows users to check balance, deposit money, withdraw money, and exit.

**Code:**
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double balance = 1000.0;
        int choice;

        do {
            System.out.println("ATM Menu:");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("Your balance is $" + balance);
                    break;
                case 2:
                    System.out.print("Enter deposit amount: ");
                    double deposit = scanner.nextDouble();
                    balance += deposit;
                    System.out.println("Your new balance is $" + balance);
                    break;
                case 3:
                    System.out.print("Enter withdrawal amount: ");
                    double withdrawal = scanner.nextDouble();
                    if (withdrawal <= balance) {
                        balance -= withdrawal;
                        System.out.println("Your new balance is $" + balance);
                    } else {
                        System.out.println("Insufficient balance.");
                    }
                    break;
                case 4:
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        } while (choice != 4);
    }
}
```

**Explanation:**
- The program uses a `do-while` loop to display an ATM menu repeatedly.
- It allows the user to check balance, deposit money, withdraw money, or exit the system.
- It uses a `switch` statement to handle the user's choice and perform the appropriate action.

