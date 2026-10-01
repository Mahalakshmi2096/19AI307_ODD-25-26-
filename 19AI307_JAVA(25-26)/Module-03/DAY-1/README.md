# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
Create a Super class Person with fields name and age. Create a subclass Student that inherits from Person and adds a field marks (integer). Implement a method in Student called calculateGrade() which returns the grade based on the marks:

Marks ≥ 90: Grade A

Marks ≥ 75 and < 90: Grade B

Marks ≥ 50 and < 75: Grade C

Marks < 50: Grade F

## AIM:
To demonstrate inheritance in Java by creating a Person superclass and a Student subclass that calculates a student's grade based on marks.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Person class with name and age, and extend it using the Student class with an additional marks field.
4. Initialize the inherited and student-specific fields using constructors.
5. Implement calculateGrade() using conditional statements based on the marks.
6. Create a Student object, calculate the grade, and display all details.


## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:

```
import java.util.Scanner;
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Student extends Person {
    int marks;

    Student(String name, int age, int marks) {
        super(name, age);
        this.marks = marks;
    }

    String calculateGrade() {
        if (marks >= 90) {
            return "A";
        } else if (marks >= 75) {
            return "B";
        } else if (marks >= 50) {
            return "C";
        } else {
            return "F";
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        String name = sc.nextLine();
        int age = sc.nextInt();
        int marks = sc.nextInt();
        Student s=new Student(name,age,marks);

        System.out.println("Name: " + s.name);
        System.out.println("Age: " + s.age);
        System.out.println("Marks: " + s.marks);
        System.out.println("Grade: " + s.calculateGrade());
    }
}
```


## OUTPUT:
<img width="502" height="592" alt="image" src="https://github.com/user-attachments/assets/548d7be1-e429-4fc4-8fb9-6fac8d6319c4" />


## RESULT:
Thus, the Java program successfully demonstrates inheritance and calculates the student's grade based on the given marks.


# Ex.No:3(b) POLYMORPHISM

## QUESTION:
Write a Java program that calculates the area of different shapes using method overloading. Create a class AreaCalculator with:

area(int side) for square

area(int length, int breadth) for rectangle

area(double radius) for circle


## AIM:
To demonstrate inheritance in Java by creating a Person superclass and a Student subclass that calculates a student's grade based on marks.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Person class with name and age, and extend it using the Student class with an additional marks field.
4. Initialize the inherited and student-specific fields using constructors.
5. Implement calculateGrade() using conditional statements based on the marks.
6. Create a Student object, calculate the grade, and display all details.

## PROGRAM:
 ```
/*
Program to implement a Polymorphism using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
class AreaCalculator {
    int area(int side) {
        return side * side;
    }
  
    int area(int length, int breadth) {
        return length * breadth;
    }

    double area(double radius) {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int side = sc.nextInt();
        int length = sc.nextInt();
        int breadth = sc.nextInt();
        double radius = sc.nextDouble();
        AreaCalculator obj = new AreaCalculator();
        System.out.println("Area of square: " + obj.area(side));
        System.out.println("Area of rectangle: " + obj.area(length, breadth));
        System.out.println("Area of circle: " + obj.area(radius));
       
    }
}
```


## OUTPUT:

<img width="960" height="379" alt="image" src="https://github.com/user-attachments/assets/4c5c5359-880d-41b4-a824-634caacceb64" />


## RESULT:
Thus, the Java program successfully demonstrates inheritance and calculates the student's grade based on the given marks.


# Ex.No:3(C) ABSTRACTION

## QUESTION:
Create abstract class BankAccount with method calculateInterest(). Extend it in SavingsAccount and FixedDepositAccount.

## AIM:
To demonstrate abstraction and runtime polymorphism by creating an abstract BankAccount class and implementing calculateInterest() in SavingsAccount and FixedDepositAccount.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an abstract BankAccount class with the abstract method calculateInterest().
4. Extend it with SavingsAccount and FixedDepositAccount, implementing the interest calculation for each.
5. Read the user's choice and corresponding account details, then create the appropriate object.
6. Call calculateInterest() and display the interest rounded to 2 decimal places.

## PROGRAM:
 ```
/*
Program to implement a Abstraction using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

abstract class BankAccount {
    abstract double calculateInterest();
}

class SavingsAccount extends BankAccount {
    double balance;

    SavingsAccount(double balance) {
        this.balance = balance;
    }

    double calculateInterest() {
        return balance * 0.04; 
    }
}

class FixedDepositAccount extends BankAccount {
    double amount;
    int years;

    FixedDepositAccount(double amount, int years) {
        this.amount = amount;
        this.years = years;
    }

    double calculateInterest() {
        return amount * 0.07 * years; 
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int choice = sc.nextInt();
        BankAccount account;
        if (choice == 1) {
            double balance = sc.nextDouble();
            account = new SavingsAccount(balance);
        } else {
            double amount = sc.nextDouble();
            int years = sc.nextInt();
            account = new FixedDepositAccount(amount, years);
        }
        System.out.printf("%.2f", account.calculateInterest());
    }
}

```

## OUTPUT:
<img width="431" height="363" alt="image" src="https://github.com/user-attachments/assets/b2f15571-8a43-43f6-907f-f84cb3eabd5d" />

## RESULT:
Thus, the Java program successfully demonstrates abstraction and runtime polymorphism by calculating interest for different types of bank accounts.



# Ex.No:3(D)    INTERFACE 

## QUESTION:
You are programming bots that analyze weather data. Each bot must implement a common interface and give a prediction.

 Bot Types:

SunBot: Predicts "HOT" if temperature > 30, else "MODERATE".

RainBot: Predicts "COLD" if temperature < 20, else "WARM".

## AIM:
To demonstrate interface-based polymorphism by creating a common WeatherBot interface and implementing it using SunBot and RainBot.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a WeatherBot interface with the predict() method and implement it in SunBot and RainBot.
4. Read the temperature and bot type from the user.
5. Create the appropriate bot object based on the bot type.
6. Call predict() and display the weather prediction.

## PROGRAM:
 ```
/*
Program to implement a Interface using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
interface WeatherBot {
    String predict(int temperature);
}

class SunBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature > 30) {
            return "HOT";
        } else {
            return "MODERATE";
        }
    }
}

class RainBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature < 20) {
            return "COLD";
        } else {
            return "WARM";
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int temperature = sc.nextInt();
        int botType = sc.nextInt();
        WeatherBot bot;
        if (botType == 1) {
            bot = new SunBot();
        } else {
            bot = new RainBot();
        }
        System.out.println(bot.predict(temperature));
        sc.close();
    }
}
```


## OUTPUT:

<img width="400" height="168" alt="image" src="https://github.com/user-attachments/assets/fc4c6238-5c9f-4ac7-bf0a-a0e7f60d7c2e" />


## RESULT:
Thus, the Java program successfully demonstrates interface implementation and polymorphism to generate weather predictions.
 


# Ex.No:3(E) INNER CLASS

## QUESTION:
Write a Java program to demonstrate an inner class by creating a class Inner inside an Outer class and accessing a variable of the outer class.

## AIM:
To write a Java program to demonstrate the use of an inner class and access the members of the outer class

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an Outer class with an integer variable and define an Inner class inside it.
4. Create a display() method in the inner class to access the outer class variable.
5. Create objects of the Outer and Inner classes.
6. Call the display() method and print the value.


## PROGRAM:
 ```
/*
Program to implement a InnerClass using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:

```
class Outer {
    int number = 10;

    class Inner {
        void display() {
            System.out.println("Number: " + number);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner();
        inner.display();
    }
}
```

## OUTPUT:
<img width="387" height="129" alt="image" src="https://github.com/user-attachments/assets/a06af543-b5ce-4b77-b17a-3dbe6948ce28" />


## RESULT:
Thus, the Java program successfully demonstrates the creation and use of an inner class in Java.



# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Write a Java program to check if a number is an Armstrong number using Math.pow() and the Integer wrapper class. Take input from the user.

## AIM:
To write a Java program to check whether a given number is an Armstrong number using Math.pow() and the Integer wrapper class.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number as input and use the Integer wrapper class to obtain its value.
4. Count the number of digits and extract each digit from the number.
5. Use Math.pow() to calculate the sum of each digit raised to the number of digits.
6. Compare the sum with the original number and display whether it is an Armstrong number.



## PROGRAM:
 ```
/*
Program to implement a Wrapper Class using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String input = sc.nextLine();
        Integer num = Integer.valueOf(input);

        int original = num;
        int digits = input.length();
        int sum = 0;
        int temp = num;

        while (temp != 0) {
            int digit = temp % 10;
            sum += (int) Math.pow(digit, digits);
            temp /= 10;
        }

        if (sum == original)
            System.out.println(original + " is an Armstrong number.");
        else
            System.out.println(original + " is not an Armstrong number.");

        
    }
}
```
## OUTPUT:
<img width="867" height="252" alt="image" src="https://github.com/user-attachments/assets/d6ccd49d-ff14-4ce8-b35d-0ba4fb3fbde3" />


## RESULT:
Thus, the Java program successfully checks whether the given number is an Armstrong number using Math.pow() and the Integer wrapper class.

