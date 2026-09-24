# Ex.No:1(A) INTRODUCTION TO JAVA PROGRAMMING, DATA TYPES, VARIABLES AND OPERATORS

## QUESTION:
Lovely has mastered printing in Java, and now she wants to learn how arithmetic operators work. She’s curious about how Java can add, subtract, multiply, divide, and find remainders of two numbers.

Write a Java program that:

Accepts two integer numbers from the user.

Demonstrates all 5 arithmetic operations:

Addition (+)

Subtraction (-)

Multiplication (*)

Division (/)

Modulus (%)

Displays the result of each operation in a separate line with a clear message.

## AIM:

To write a Java program that reads two integer numbers from the user and performs basic arithmetic operations such as addition, subtraction, multiplication, division, and modulus, and displays the results.

## ALGORITHM :


Start the program.

Create an object of the Scanner class to take input from the user.

Read the first integer input from the user and store it in variable num1.

Read the second integer input from the user and store it in variable num2.

Calculate the sum of num1 and num2, and display the result.

Calculate the difference (num1 - num2), and display the result.

Calculate the product of num1 and num2, and display the result.

Calculate the quotient of num1 divided by num2, and display the result.

Calculate the remainder of num1 divided by num2, and display the result.

Close the Scanner object.




## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## Sourcecode.java:

    import java.util.Scanner;
    
    public class ArithmeticOperations {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
    
            int num1 = sc.nextInt();
            int num2 = sc.nextInt();
    
            System.out.println("Sum = " + (num1 + num2));
            System.out.println("Difference = " + (num1 - num2));
            System.out.println("Product = " + (num1 * num2));
            System.out.println("Quotient = " + (num1 / num2));
            System.out.println("Remainder = " + (num1 % num2));
    
            sc.close();
        }
    }





## OUTPUT:
<img width="692" height="287" alt="image" src="https://github.com/user-attachments/assets/b9ecf71b-325c-4c72-a6e6-ce3ad8b4ba11" />



## RESULT:
Therefore the program has been executed successfully.
