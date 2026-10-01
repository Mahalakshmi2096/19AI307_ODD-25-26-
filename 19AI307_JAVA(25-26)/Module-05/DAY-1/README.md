# Ex.No:5(A) INPUTSTREAMREADER 
## NAME: MAHALAKSHMI B
## REG NO: 212224040182
## QUESTION:
Write a program to demonstrate chaining of streams (BufferedReader on top of InputStreamReader on top of System.in)
<img width="296" height="175" alt="image" src="https://github.com/user-attachments/assets/55523e5e-80b1-4fdd-9556-350840f0033c" />

## AIM:
To write a Java program that demonstrates stream chaining by connecting System.in → InputStreamReader → BufferedReader to read user input and display the entered details.

## ALGORITHM :
1. Start the program.

2. Import the necessary I/O packages (java.io.*).

3. Create a BufferedReader object by chaining System.in → InputStreamReader → BufferedReader.

4. Read the user's name using the readLine() method.

5. Read the user's age using the readLine() method.

6. Display the collected user details (name and age).

7. Handle any IOException that may occur during input operations.


## SOURCE CODE:
```
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ChainingStreamsExample {
    public static void main(String[] args) {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        try {
            String name = br.readLine();
            String age = br.readLine();
            System.out.println("--- User Details ---");
            System.out.println("Name: " + name);
            System.out.println("Age: " + age);
        } catch (IOException e) {
            System.out.println("Error reading input");
        }
    }
}
```

## OUTPUT:
<img width="631" height="496" alt="image" src="https://github.com/user-attachments/assets/eab75048-8fc2-4f89-885e-bf2ccf76e182" />


## RESULT:
The program successfully demonstrates chaining of input streams using BufferedReader and InputStreamReader. It reads the user's name and age from the console and displays them without errors.


# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.
<img width="690" height="260" alt="image" src="https://github.com/user-attachments/assets/009cda3f-7124-4cfe-af33-bb8be9b4e19a" />

## AIM:
To write a Java program that demonstrates object serialization and deserialization, where multiple Student objects entered by the user are stored in a file and later retrieved and displayed.

## ALGORITHM :
1. Start the program and import required I/O and utility packages.

2. Create a Student class that implements Serializable.

3. Read the number of students and their details from the user and store them in a list.

4. Open an ObjectOutputStream and write the list of Student objects to a file.

5. Open an ObjectInputStream and read back the list of Student objects from the file.

6. Display the deserialized student details on the screen.

7. Handle all I/O exceptions that occur during serialization and deserialization.


## SOURCE CODE:
```
import java.io.*;
import java.util.*;

// Student class must implement Serializable
class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class StudentSerializationUserInput {

    // Serialize list of students
    public static void serializeStudents(List<Student> students, String fileName) {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) {
            oos.writeObject(students);
            System.out.println("Students serialized successfully into: " + fileName);
        } catch (IOException e) {
            System.out.println("Error during serialization: " + e.getMessage());
        }
    }

    // Deserialize list of students
    @SuppressWarnings("unchecked")
    public static List<Student> deserializeStudents(String fileName) {
        List<Student> students = null;
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) {
            students = (List<Student>) ois.readObject();
            System.out.println("Students deserialized successfully from: " + fileName);
        } catch (IOException | ClassNotFoundException e) {
            System.out.println("Error during deserialization: " + e.getMessage());
        }
        return students;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        List<Student> students = new ArrayList<>();

        int n = scanner.nextInt();
        scanner.nextLine(); // consume newline

        // Read student details
        for (int i = 0; i < n; i++) {
            int id = scanner.nextInt();
            scanner.nextLine();
            String name = scanner.nextLine();
            double marks = scanner.nextDouble();
            scanner.nextLine();
            students.add(new Student(id, name, marks));
        }

        String fileName = "students.dat";

        // Serialize
        serializeStudents(students, fileName);

        // Deserialize
        List<Student> deserializedStudents = deserializeStudents(fileName);

        // Display deserialized data
        if (deserializedStudents != null) {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) {
                System.out.println(s);
            }
        }

        scanner.close();
    }
}
```


## OUTPUT:

<img width="1242" height="449" alt="image" src="https://github.com/user-attachments/assets/3b1213d3-934c-4356-9b52-f1f29494a618" />

## RESULT:
The program successfully serializes a list of Student objects into a file named students.dat and then deserializes the data back into a list. It correctly displays all the retrieved student information, proving that object serialization and deserialization work as expected.


# Ex.No:5(C)  FILE HANDLING USING JAVA

## QUESTION:
Write a Java program to create a new file named example.txt.

 <img width="290" height="147" alt="image" src="https://github.com/user-attachments/assets/a6a67b4f-be79-4940-8ee1-e0c734a79fa5" />

## AIM:
To write a Java program that demonstrates basic file handling by creating a new file using the File class and the createNewFile() method.

## ALGORITHM :
1. Start the program and import the required java.io.File package.

2. Create a File object and specify the filename to be created.

3. Call the createNewFile() method to attempt file creation.

4. Check if the file is successfully created.

5. If created, display the file name to the user.

6. Handle any exceptions that may occur during file creation.

7. End the program.	



## PROGRAM:

## SOURCE CODE:

```
import java.io.File;

public class CreateFileExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
## OUTPUT:
<img width="740" height="195" alt="image" src="https://github.com/user-attachments/assets/43e4a17c-1424-4fa2-84b0-c186a1eb5a7e" />


## RESULT:
The program successfully creates a new file named example.txt in the project directory. If the file already exists, the program simply terminates without creating a duplicate.



# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for determine the priority and name of the current thread.

Note : Read the threadname from the User

For example:

<img width="381" height="161" alt="image" src="https://github.com/user-attachments/assets/019048d4-1291-4ab6-9864-8f3930b7c6e2" />


## AIM:
To write a Java program that reads a thread name from the user, sets the current thread’s name, and displays its priority and full thread details.

## ALGORITHM :
1. Start the program and import the necessary utilities.

2. Read a thread name from the user using a Scanner.

3. Retrieve the current thread using Thread.currentThread().

4. Set the name of the current thread using setName().

5. Obtain the thread’s priority using getPriority().

6. Display the thread’s name, priority, and full thread information.

7. End the program.





## PROGRAM:


## SOURCE CODE:
```
import java.util.Scanner;

public class CurrentThreadDetails {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String threadName = sc.nextLine();
        Thread t = Thread.currentThread();
        t.setName(threadName);
        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());
        System.out.println(t);
    }
}
```


## OUTPUT:

<img width="726" height="217" alt="image" src="https://github.com/user-attachments/assets/fac09833-9da1-4690-b348-d30704a60185" />


## RESULT:

The program successfully reads a custom name for the current thread, assigns it to the running thread, and displays the thread’s priority and complete thread details.


# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Maintain two int variables a and b, read their initial values from user. Use synchronized block to swap them and print swapped values.
- Input:
- Two lines: a and b values
- Output:
- a = <swapped_a>
- b = <swapped_b>

<img width="185" height="162" alt="image" src="https://github.com/user-attachments/assets/c9690119-ce26-4bcb-89da-79fcab248c3e" />

## AIM:
To write a Java program that demonstrates the use of the synchronized block by swapping two numbers safely using a lock object.

## ALGORITHM :
1. Start the program and import the required utility package.

2. Read two integer values from the user.

3. Create a lock object to control synchronization.

4. Use a synchronized block with the lock object.

5. Inside the synchronized block, swap the values of the two variables using a temporary variable.

6. After swapping, display the updated values of both variables.

7. End the program.	


## SOURCE CODE:

```
import java.util.Scanner;

public class SwapUsingSync {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int b = sc.nextInt();

        Object lock = new Object();

        synchronized (lock) {
            int temp = a;
            a = b;
            b = temp;
        }

        System.out.println("a = " + a);
        System.out.println("b = " + b);
    }
}
```


## OUTPUT:

<img width="433" height="343" alt="image" src="https://github.com/user-attachments/assets/1491b8d1-93ef-43fc-98a6-b4bb3af230ae" />


## RESULT:
The program successfully demonstrates synchronization by swapping two numbers within a synchronized block, ensuring thread-safe execution even though only one thread is used.

