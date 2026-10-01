# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
Write a program that reads two integers and divides the first by the second. Handle the case when division by zero occurs.

## AIM:
To write a Java program that reads two integers and divides the first integer by the second, while handling division-by-zero errors using exception handling.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Scanner object to read input.
4. Read two integers, a and b.
5. Use a try block to divide a by b.
6. If division is successful, display the result.
7. If b is zero, catch the ArithmeticException.
8. Display an error message: "Error: Division by zero".
9. Stop the program.



## PROGRAM:
 ```
/*
Program to implement a Exception Handling using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:

```
import java.util.Scanner;
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int a= sc.nextInt();
        int b=sc.nextInt();
        try{
            int c=a/b;
            System.out.println("Result: "+c);
        }catch(ArithmeticException e){
            System.out.println("Error: Division by zero");
        }
    }
}
```

## OUTPUT:

<img width="696" height="312" alt="image" src="https://github.com/user-attachments/assets/439b54be-52d9-4c59-a0ab-61ed8eeb498c" />


## RESULT:
The program was executed successfully. It correctly performs division when the second number is non-zero and handles the division-by-zero exception by displaying an appropriate error message.


# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
In a gaming lounge, there is only one master console power switch that controls all gaming consoles. Whenever a player turns on any console, it internally triggers the master power. The master switch must ensure only one instance is ever created, regardless of how many times it's accessed, to prevent power fluctuations.
Every time a player accesses the master switch, it logs an access count. Since the switch is Singleton, the count should increment globally and reflect shared state.

## AIM:
To develop a Java program that manages a master console power switch shared by all gaming consoles and maintains a common access count whenever a player accesses it.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class to manage the Master Power Switch.
4. Ensure that the same Master Power Switch is shared whenever it is accessed.
5. Initialize the access count to zero.
6. Read the number of players.
7. For each player, read the player's name.
8. Access the Master Power Switch.
9. Increment the common access count.
10. Display the player's name and the total number of accesses so far.
11. Repeat the process for all players.
12. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a SOLID Principles in Java Program
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:
```
import java.util.*;

class MasterPowerSwitch {
    private static MasterPowerSwitch instance;
    private int count;
    private MasterPowerSwitch(){
        this.count=0;
    }
    public static MasterPowerSwitch getInstance(){
        if(instance==null){
            instance=new MasterPowerSwitch();
        }
        return instance;
    }
    public int logAccess(){
        this.count++;
        return this.count;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String player = sc.nextLine();
            MasterPowerSwitch power = MasterPowerSwitch.getInstance();
            int count = power.logAccess();
            System.out.println(player + " accessed Master Power Switch. Total accesses so far: " + count);
        }
    }
}

```


## OUTPUT:

<img width="1246" height="255" alt="image" src="https://github.com/user-attachments/assets/f762f799-860e-46ab-999e-46b5c390160d" />


## RESULT:
The program was executed successfully. The Master Power Switch was shared among all players, and the access count was updated globally for each access.


# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Implement a system where a Library contains multiple Book objects. Each Book is created inside the Library. Books can't exist independently (Composition).

## AIM:
To develop a Java program that models a Library containing multiple Book objects, where books are created and managed within the Library.
## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Library object.
4. Read the number of books.
5. Repeat for each book:
6. Read the book title.
7. Read the author name.
8. Create the Book object inside the Library.
9. Add the book to the collection.
10. Display the details of all books in the Library.
11. Stop the program

## PROGRAM:
 ```
/*
Program to implement a Composition Concepts in Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:
```
import java.util.*;

public class CompositionExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Library library = new Library();
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String title = sc.nextLine();
            String author = sc.nextLine();
            library.addBook(title, author);
        }
        library.showBooks();
        sc.close();
    }
}
class Book {
    private String title;
    private String author;
    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
    public String getDetails() {
        return title + " by " + author;
    }
}
class Library {
     ArrayList<Book> books = new ArrayList<>();
    public void addBook(String title, String author) {
        Book b = new Book(title, author);
        books.add(b);
    }

    public void showBooks() {
        System.out.println("Books in Library:");
        for (Book b : books) {
            System.out.println("- " + b.getDetails());
        }    
    }
}

```

## OUTPUT:
<img width="885" height="518" alt="image" src="https://github.com/user-attachments/assets/7084df60-6a07-4528-84b0-ddb5c14fab74" />



## RESULT:
The program was executed successfully. The Library managed multiple Book objects, and the details of all books were displayed correctly.



# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
You are asked to simulate a simple Shape Drawing Tool using the Factory Design Pattern in Java.

You will implement a Shape interface with concrete classes for different shapes (Circle, Square, Rectangle). Using a ShapeFactory, your program will take shape names from user input and draw them accordingly. If the shape is unknown, print an error message.


## AIM:
To write a Java program that implements the Factory Design Pattern to create and draw shapes dynamically based on user input.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Shape interface containing a draw() method.
4. Create concrete classes Circle, Square, and Rectangle implementing Shape.
5. Create a ShapeFactory class with a method getShape(String shapeType).
6. In the main() method, accept user input for shape type.
7. Call factory method to get the appropriate object.
8. Draw the shape or print error if unknown.
9. Stop the program.


## PROGRAM:
```
Developed By: MAHALAKSHMI B
RegisterNumber: 212224040182
```

## SOURCE CODE:
```
import java.util.Scanner;

interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class ShapeFactory {
    public Shape getShape(String shapeType) {
        if (shapeType == null) {
            return null;
        }
        switch (shapeType.toLowerCase()) {
            case "circle":
                return new Circle();
            case "square":
                return new Square();
            case "rectangle":
                return new Rectangle();
            default:
                return null;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ShapeFactory factory = new ShapeFactory();
        
        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) {
                break;
            }
            
            Shape shape = factory.getShape(input);
            if (shape != null) {
                shape.draw();
            } else {
                System.out.println("Invalid shape: " + input);
            }
        }
        sc.close();
    }
}
```



## OUTPUT:

![java44](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/b628a27d8352a971924fad5b0adffc7f5f8644ba/19AI307_JAVA(25-26)/Module-04/DAY-4/java44.png)

## RESULT:
Thus, the Java program to simulate Shape Drawing using the Factory Design Pattern was successfully implemented and executed.



# Ex.No:4(E) DESIGN PATTERN  ---- BEHAVIOUR PATTERN
## NAME: MAHALAKSHMI B
## REG NO: 212224040182
## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.


## AIM:
To write a Java program that demonstrates a Behavioral Pattern using the Factory Method, allowing different notification types to send messages through a common interface.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an interface Notification with method notifyUser().
4. Implement concrete classes: EmailNotification, SMSNotification, and PushNotification.
5. Create a NotificationFactory that returns the appropriate object based on user input.
6. In main(), get the notification type from the user.
7. Call the notifyUser() method of the returned object.
8. If no valid type is provided, display an error.
9. Stop the program.


## SOURCE CODE:
```
import java.util.Scanner;

interface Notification {
    void notifyUser();
}

// ===== Concrete Notifications =====
class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

// ===== Factory =====
class NotificationFactory {
    public Notification createNotification(String type) {
        if (type == null) return null;
        switch (type.toLowerCase()) {
            case "email":
                return new EmailNotification();
            case "sms":
                return new SMSNotification();
            case "push":
                return new PushNotification();
            default:
                return null;
        }
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationFactory factory = new NotificationFactory();

        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) break;

            Notification n = factory.createNotification(input);
            if (n != null) {
                n.notifyUser();
            } else {
                System.out.println("Invalid notification type: " + input);
            }
        }

        sc.close();
    }
}
```


## OUTPUT:

![java45](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c6316a5904f4a174dd995f6b7d7c47b65f677921/19AI307_JAVA(25-26)/Module-04/DAY-5/java45.png)

## RESULT:
Thus, the program demonstrating the Behavioral Pattern using Factory Method to generate different notification types was successfully implemented and executed.



