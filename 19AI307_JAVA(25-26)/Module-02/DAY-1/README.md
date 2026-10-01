# Ex.No:2(A) CLASS AND OBJECT

## QUESTION:
Create a class Car with attributes brand, model, year. Create 2 objects and print their details.

## AIM:
To create a Java class Car with attributes brand, model, and year, create two objects, and display their details.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Car class with brand, model, and year attributes.
4. Create two Car objects and assign values to their attributes.
5. Display the details of both car objects.
6. Stop the program.

## PROGRAM:
 ```
/*
Program to implement a Class and Objects using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:

```
class Car{
    String brand;
    String model;
    int year;
}
public class prog {
    public static void main(String[] args) {
        Car car1 = new Car();
        car1.brand = "Toyota";
        car1.model = "Innova";
        car1.year = 2022;

        Car car2 = new Car();
        car2.brand = "Hyundai";
        car2.model = "i20";
        car2.year = 2021;

        System.out.println("Car 1: " + car1.brand + " " + car1.model + " " + car1.year);
        System.out.println("Car 2: " + car2.brand + " " + car2.model + " " + car2.year);
    }
}

```

## OUTPUT:
<img width="798" height="309" alt="image" src="https://github.com/user-attachments/assets/c58e337c-c13d-4284-853e-1f3d8f53bbfc" />


## RESULT:
Thus, the Java program successfully creates two Car objects and displays their details.


# Ex.No:2(B) METHODS

## QUESTION:
Write a method int square (int number) that returns the square of a given number.

## AIM:
To write a Java method square (int number) that calculates and returns the square of a given number.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Define a method square() that accepts an integer number.
4. Calculate the square by multiplying number by itself.
5. Return the calculated value.
6. Display the returned square value.


## PROGRAM:
 ```
/*
Program to implement a Methods using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:

```
import java.util.Scanner;
public class Main{
    int square(int num){
        return num*num;
    }
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        Main o=new Main();
        System.out.println(o.square(n));
    }
}
```


## OUTPUT:

<img width="468" height="226" alt="image" src="https://github.com/user-attachments/assets/15cd2458-d78f-43e3-8cd1-e8e6a94b0b4d" />


## RESULT:
Thus, the Java method successfully calculates and returns the square of the given number.


# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:

Write a Java program to create a class called Circle with a private instance variable radius. Provide public getter and setter methods to access and modify the radius variable. However, provide two methods called calculateArea() and calculatePerimeter() that return the calculated area and perimeter based on the current radius value. 


## AIM:
To create a Java Circle class with a private radius variable and public getter, setter, area, and perimeter methods.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Circle class with a private radius and public getter and setter methods.
4. Define methods to calculate the area and perimeter using the current radius.
5. Read the radius, set it using the setter, and calculate the area and perimeter.
6. Display the radius, area, and perimeter.

## PROGRAM:
 ```
/*
Program to implement a Access Specifiers using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

class Circle {
    private double radius;

  
    public double getRadius() {
        return radius;
    }

   
    public void setRadius(double radius) {
        this.radius = radius;
    }

    
    public double calculateArea() {
        return Math.PI * radius * radius;
    }

   
    public double calculatePerimeter() {
        return 2 * Math.PI * radius;
    }
}

public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        Circle cir=new Circle();
        double radius = sc.nextDouble();
        cir.setRadius(radius);
        System.out.printf("Radius: %.2f\n" ,cir.getRadius());
        System.out.printf("Area: %.2f\n", cir.calculateArea());
        System.out.printf("Perimeter: %.2f\n", cir.calculatePerimeter());
        
    }    
}
```


## OUTPUT:
<img width="644" height="304" alt="image" src="https://github.com/user-attachments/assets/2fc36f94-edec-4b4d-a0f7-b7e42911a923" />

## RESULT:
Thus, the Java program successfully calculates and displays the area and perimeter of the circle using the given radius.


# Ex.No:2(D) VARIABLE SCOPE AND CONSTRUCTOR

## QUESTION:
Write a Java program to demonstrate a parameterized constructor.

## AIM:
To write a Java program to demonstrate the use of a parameterized constructor by initializing and displaying employee details.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an Employee class with name and id attributes.
4. Define a parameterized constructor to initialize the employee details.
5. Read the employee name and ID, then create an object using the constructor.
6. Display the employee name and ID.

## PROGRAM:
 ```
/*
Program to implement a Variable scope and Constructor using Java
Developed by: MAHALAKSHMI B
RegisterNumber:  212224040182
*/
```

## SOURCE CODE:
```
import java.util.Scanner;
class Employee{
    String name;
    int id;
    Employee(String name, int id){
        this.name=name;
        this.id=id;
        
    }
    void disp(){
        System.out.println("Employee Name: "+name);
        System.out.println("Employee ID: "+id);
    }
}
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        
        String name=sc.nextLine();
        int id=sc.nextInt();
        Employee emp=new Employee(name,id);
        emp.disp();
    }
    
}
```


## OUTPUT:
<img width="663" height="336" alt="image" src="https://github.com/user-attachments/assets/ccde0392-ee42-48a7-8620-62d8c2c54902" />



## RESULT:
Thus, the Java program successfully demonstrates a parameterized constructor and displays the initialized employee details.


# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:
Create a class College with a final variable universityName = "Saveetha University". Create objects and print the name.
## AIM:
 To create a class College with a final variable universityName = "Saveetha University". Create objects and print the name.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a College class with a final variable universityName.
4. Assign "Saveetha University" to the final variable.
5. Create an object of the College class.
6. Access and display the value of the final variable.
## PROGRAM:
 ```
/*
Program to implement a Access Modifiers using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:

```
import java.util.*
class College {
    final String universityName = "Saveetha University";
}

class prog {
    public static void main(String[] args) {
       College c=new College();
       System.out.println(c.universityName);
    }
}
```

## OUTPUT:
<img width="630" height="185" alt="image" src="https://github.com/user-attachments/assets/c7ed5ac4-6543-4150-bd5f-9983425e7772" />


## RESULT:
Thus, the Java program successfully demonstrates the use of the final keyword to create a constant variable.

