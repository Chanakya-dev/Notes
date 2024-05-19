# 1. Introduction to Java Programming and Hello World

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}

```

# 2. Variables and Data Types

```java
// Add variables and data types
String name = "John";
int age = 25;
double score = 85.5;

```

Updated program:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);
    }
}

```

# 3. Basic Input and Output

```java
// Add basic input and output
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String inputName = scanner.nextLine();

```

Updated program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String inputName = scanner.nextLine();

        System.out.println("Nice to meet you, " + inputName + "!");
    }
}

```

# 4. Conditional Statements (if/else)

```java
// Add conditional statements
if (age >= 18) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are a minor.");
}

```

Updated program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String inputName = scanner.nextLine();

        System.out.println("Nice to meet you, " + inputName + "!");

        if (age >= 18) {
            System.out.println("You are an adult.");
        } else {
            System.out.println("You are a minor.");
        }
    }
}

```

# 5. Loops (for loop and while loop)

```java
// Add loops
for (int i = 1; i <= 5; i++) {
    System.out.println("Count: " + i);
}

int count = 0;
while (count < 3) {
    System.out.println("While count: " + count);
    count++;
}

```

Updated program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String inputName = scanner.nextLine();

        System.out.println("Nice to meet you, " + inputName + "!");

        if (age >= 18) {
            System.out.println("You are an adult.");
        } else {
            System.out.println("You are a minor.");
        }

        for (int i = 1; i <= 5; i++) {
            System.out.println("Count: " + i);
        }

        int count = 0;
        while (count < 3) {
            System.out.println("While count: " + count);
            count++;
        }
    }
}

```

# 6. Methods

```java
// Add a method
public static void greet(String name) {
    System.out.println("Hello, " + name + "!");
}

```

Updated program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String inputName = scanner.nextLine();

        greet(inputName);

        if (age >= 18) {
            System.out.println("You are an adult.");
        } else {
            System.out.println("You are a minor.");
        }

        for (int i = 1; i <= 5; i++) {
            System.out.println("Count: " + i);
        }

        int count = 0;
        while (count < 3) {
            System.out.println("While count: " + count);
            count++;
        }
    }

    public static void greet(String name) {
        System.out.println("Hello, " + name + "!");
    }
}

```

# 7. Classes and Objects

```java
// Add a class
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("My name is " + name + " and I'm " + age + " years old.");
    }
}

```

Updated program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");

        String name = "John";
        int age = 25;
        double score = 85.5;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Score: " + score);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String inputName = scanner.nextLine();

        greet(inputName);

        if (age >= 18) {
            System.out.println("You are an adult.");
        } else {
            System.out.println("You are a minor.");
        }

        for (int i = 1; i <= 5; i++) {
            System.out.println("Count: " + i);
        }

        int count = 0;
        while (count < 3) {
            System.out.println("While count: " + count);
            count++;
        }

        Person person1 = new Person("Alice", 30);
        Person person2 = new Person("Bob", 20);

        person1.introduce();
        person2.introduce();
    }

    public static void greet(String name) {
        System.out.println("Hello, " + name + "!");
    }
}

class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("My name is " + name + " and I'm " + age + " years old.");
    }
}

```