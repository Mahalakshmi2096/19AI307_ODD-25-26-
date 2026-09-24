# Ex.No:1(C) LOOPING STATEMENT

## QUESTION:

Display Factors of a Number

## AIM:

To write a Java program that reads an integer from the user and displays all the factors of the given number.


## ALGORITHM :


1.Start the program and read an integer n from the user.

2.Loop from 1 to n and check if each number i divides n exactly (i.e., n % i == 0).

3.If yes, print i as a factor.

4.Continue the loop until all factors are printed.

5.End the program.



## PROGRAM:
 ```
/*
Program to implement a Looping Statement using Java
Developed by: MAHALAKSHMI B
RegisterNumber: 212224040182
*/
```

## SOURCE CODE:


    import java.util.Scanner;
    
    public class Factors {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int n = sc.nextInt();
    
            System.out.print("Factors: ");
            for (int i = 1; i <= n; i++) {
                if (n % i == 0) { 
                    System.out.print(i + " ");
                }
            }
        }
    }




## OUTPUT:

<img width="841" height="350" alt="image" src="https://github.com/user-attachments/assets/6bef1e00-0a98-4c85-a146-b1354240eb4f" />


## RESULT:
Therefore, the program successfully reads a number from the user and computes its factors.

