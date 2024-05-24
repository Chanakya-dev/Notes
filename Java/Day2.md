### **Day 2: Basic Input/Output and Control Flow (Part 1) (2 Hours)**

#### **Objective:**
- Learn how to take user input and display output.
- Understand and implement conditional statements using `if` and `else`.
- Introduce logical operators (`&&`, `||`, `!`) to combine conditions.

#### **Schedule:**

**First Hour:**

1. **Review of Day 1 (10 minutes):**
    - Brief recap of the basic structure of a Java program, variables, and data types.
    - Quick review of the "Hello, World!" program with variables.

2. **Introduction to Basic Input and Output (10 minutes):**
    - Explain the need for taking user input in programs.
    - Introduce the `Scanner` class for reading input from the console.
    - Demonstrate importing the `Scanner` class and creating a `Scanner` object.

    **Example:**
    ```java
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            System.out.print("Enter your name: ");
            String name = scanner.nextLine();
            System.out.println("Hello, " + name + "!");
        }
    }
    ```

3. **Live Coding Session (15 minutes):**
    - Demonstrate how to take different types of user inputs (String, int, double).
    - Show how to prompt the user for input and read the values.

    **Example:**
    ```java
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Enter your name: ");
            String name = scanner.nextLine();

            System.out.print("Enter your age: ");
            int age = scanner.nextInt();

            System.out.print("Enter your score: ");
            double score = scanner.nextDouble();

            System.out.println("Name: " + name);
            System.out.println("Age: " + age);
            System.out.println("Score: " + score);
        }
    }
    ```

4. **Hands-on Practice (25 minutes):**
    - Students modify their programs to take user input for various data types.
    - Assist students as they write and run their programs.
    - Encourage students to experiment with taking different types of input.

**Second Hour:**

5. **Introduction to Conditional Statements (if/else) (15 minutes):**
    - Explain the purpose of conditional statements in controlling the flow of a program.
    - Introduce `if` and `else` statements with examples.
    - Discuss real-world scenarios where conditional statements are used, such as checking if a user is eligible to vote.

    **Example:**
    ```java
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Enter your age: ");
            int age = scanner.nextInt();

            if (age >= 18) {
                System.out.println("You are eligible to vote.");
            } else {
                System.out.println("You are not eligible to vote.");
            }
        }
    }
    ```

6. **Live Coding Session (10 minutes):**
    - Demonstrate more complex conditions using logical operators (`&&`, `||`, `!`).
    - Explain how to combine conditions to create more sophisticated logic.

    **Example:**
    ```java
    import java.util.Scanner;

    public class Main {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            System.out.print("Enter your age: ");
            int age = scanner.nextInt();

            System.out.print("Do you have a driver's license (true/false)? ");
            boolean hasLicense = scanner.nextBoolean();

            if (age >= 18 && hasLicense) {
                System.out.println("You can drive.");
            } else if (age >= 18 && !hasLicense) {
                System.out.println("You need a driver's license to drive.");
            } else {
                System.out.println("You are not eligible to drive.");
            }
        }
    }
    ```

7. **Hands-on Practice (20 minutes):**
    - Students write programs using `if` and `else` statements to solve real-world problems, such as determining if a number is even or odd, checking if a user can vote, or evaluating grades.
    - Assist students as they implement conditional logic in their programs.
    - Encourage students to use logical operators to combine multiple conditions.

8. **Q&A Session (10 minutes):**
    - Open the floor for any questions related to the topics covered.
    - Clarify any doubts and provide additional examples if needed.

9. **Recap and Summary (5 minutes):**
    - Review key points covered during the session.
    - Emphasize the importance of user input, conditional statements, and logical operators in building interactive programs.

### **Detailed Examples and Explanations**

#### **Example 1: Checking Voting Eligibility**

**Scenario:**
- A program to determine if a user is eligible to vote based on their age.

**Code:**
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your age: ");
        int age = scanner.nextInt();

        if (age >= 18) {
            System.out.println("You are eligible to vote.");
        } else {
            System.out.println("You are not eligible to vote.");
        }
    }
}
```

**Explanation:**
- The program takes the user's age as input.
- It checks if the age is 18 or more.
- If true, it prints that the user is eligible to vote; otherwise, it prints that the user is not eligible.

#### **Example 2: Driving Eligibility**

**Scenario:**
- A program to determine if a user can drive based on their age and whether they have a driver's license.

**Code:**
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your age: ");
        int age = scanner.nextInt();

        System.out.print("Do you have a driver's license (true/false)? ");
        boolean hasLicense = scanner.nextBoolean();

        if (age >= 18 && hasLicense) {
            System.out.println("You can drive.");
        } else if (age >= 18 && !hasLicense) {
            System.out.println("You need a driver's license to drive.");
        } else {
            System.out.println("You are not eligible to drive.");
        }
    }
}
```

**Explanation:**
- The program takes the user's age and whether they have a driver's license as input.
- It checks if the user is 18 or older and has a driver's license.
- Based on the conditions, it prints whether the user can drive, needs a license, or is not eligible to drive.

#### **Example 3: Grade Evaluation**

**Scenario:**
- A program to determine a user's grade based on their score.

**Code:**
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your score: ");
        double score = scanner.nextDouble();

        if (score >= 90) {
            System.out.println("Grade: A");
        } else if (score >= 80) {
            System.out.println("Grade: B");
        } else if (score >= 70) {
            System.out.println("Grade: C");
        } else if (score >= 60) {
            System.out.println("Grade: D");
        } else {
            System.out.println("Grade: F");
        }
    }
}
```


