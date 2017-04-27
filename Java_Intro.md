IT Circle
University of Colombo - Faculty of Science

Email: jeewantha.janith@gmail.com

# Java - Intro


### Environment:
 - Java JDK 7/8 (And make sure PATH is set)
 - A text editor (Notepad, gedit...)
 - Netbeans for GUI development with Swing

### Introduction: 
 - Initiated by James Gosling 
 - 1st release in 1995
 - Originally developed by Sun Microsystems - now owned by Oracle

### Hello World

```java
public class MyFirstJavaProgram {
   public static void main(String []args) {
      System.out.println("Hello World!");
   }
}
```

Save the file as : ```MyFirstJavaProgram.java```
Open command prompt and navigate to your file's directory
```sh
cd /path/to/your/file
```
Compile :
```sh
javac MyFirstJavaProgram.java
```
Run :
```sh
java MyFirstJavaProgram
```
&nbsp;
### Java Compilation Process

![compilation process](http://www.sitesbay.com/java/images/Run-Compile/Java-Compiler.png)
&nbsp;
### Platform Independency

![Platform Independency](https://www.safaribooksonline.com/library/view/client-server-web-apps/9781449369323/images/clwa_0401.png)
&nbsp;
### Basic Syntax

About Java programs, it is very important to keep in mind the following points.

 - **Case Sensitivity** : *Java is case sensitive, which means identifier Hello and hello would have different meaning in Java*

 - **Class Names** : *For all class names the first letter should be in Upper Case. If several words are used to form a name of the class, each inner word's first letter should be in Upper Case
    Example: ```class MyFirstJavaClass```*

 - **Method Names** − *All method names should start with a Lower Case letter. If several words are used to form the name of the method, then each inner word's first letter should be in Upper Case
    Example: ```public void myMethodName()```*

 - **Program File Name** : *Name of the program file should exactly match the class name*

 - *When saving the file, you should save it using the class name (Remember Java is case sensitive) and append ```.java``` to the end of the name (if the file name and the class name do not match, your program will not compile)*

    *Example: Assume ```MyFirstJavaProgram``` is the class name. Then the file should be saved as ```MyFirstJavaProgram.java```*

 - *```public static void main(String args[])``` − Java program processing starts from the ```main()``` method which is a mandatory part of every Java program*

### Comments in Java

```java
package firstpackage;

public class MyFirstJavaProgram {

   /* This is my first java program.
    * This will print 'Hello World' as the output
    * This is an example of multi-line comments.
    */

  /**
    * The MyFirstJavaProgram program implements an application that
    * simply displays "Hello World!" to the standard output.
    *
    * @author  Janith
    * @version 1.0
    * @since   2017-03-31 
    */
   public static void main(String []args) {
      // This is an example of single line comment
      /* This is also an example of single line comment. */
      System.out.println("Hello World");
   }
}
```

### Data Types

 - Primitive Data Types
 - Reference/Object Data Types

##### Primitive Data Types
&nbsp;
![Data Types](http://java2learn.com/wp-content/uploads/2013/08/cmpdatatypes.png)
&nbsp;
##### Primitive Data Type Declaration and Initialization
&nbsp;
![Primitive Data Type Declaration and Initialization](http://3.bp.blogspot.com/-LJN2Y8O-KT0/VX7vqDj8vAI/AAAAAAAAATg/mvfsLPDgak8/s1600/literal_exp.jpg)
&nbsp;

```java
byte B = 22;             // initializes a byte type variable B.
int a, b, c;             // Declares three ints, a, b, and c.
int a = 10, b = 10;      // Example of initialization
int decimal = 100;
int octal = 0144;
int hexa =  0x64;
long l = 100L;           // notice the 'L' in long literals
float f = 5.0f           // notice the 'f' in float literals
double pi = 3.14159;     // declares and assigns a value of PI.
char ch = 'X';           // the char variable a is initialized with value 'X'
boolean success = true;  // booleans hold true or false
String text = "Java Programming...";  // Strings are not primitive, but added here
String text = "two\nlines";
String text = "This line \"has\" a quote";
```

Try this code

```java
public class Test {
   public void pupAge() {
      int age = 0;
      age = age + 7;
      System.out.println("Puppy age is : " + age);
   }

   public static void main(String args[]) {
      Test test = new Test();
      test.pupAge();
   }
}
```

##### Reference Data Types

```java
Ball b1 = new Ball();
Ball b2;
b2 = new Ball();
```
```java
public class Student {
   private String name;

   public Student ( String name_arg ) {
      name = name_arg;
   }
   
   public void printDetails(){
      System.out.println("Hi, my name is " + name);
   }
}

public class Tutor {
   public Student s1, s2;

   public Tutor ( Student st1, st2 ) {
      s1 = st1;
      s2 = st2;
   }
}

public class TutorTest {
   public static void main ( String args[] ) {
      Student student1 = new Student ( "Gautham");
      Student student2 = new Student ( "Sai");
      Tutor t = new Tutor (s1,s2);
      t.s1.printDetails();
      t.s2.printDetails();
      ////////////////////
      Tutor t1 = new Tutor ( new Student ( "Sal", 3), new Student ("Dom",4) );
   }
} 
```

```java
import java.io.*;
public class Employee {
   
   // this instance variable is visible for any child class.
   public String name;
   // salary  variable is visible in Employee class only.
   private double salary;
   
   // The name variable is assigned in the constructor.
   public Employee (String empName) {
      name = empName;
   }

   // The salary variable is assigned a value.
   public void setSalary(double empSal) {
      salary = empSal;
   }

   // This method prints the employee details.
   public void printEmp() {
      System.out.println("name  : " + name );
      System.out.println("salary :" + salary);
   }

   public static void main(String args[]) {
      Employee empOne = new Employee("Ransika");
      empOne.setSalary(1000);
      empOne.printEmp();
   }
}
```

### Methods
![Methods](http://1.bp.blogspot.com/-qQ21fDfuMio/Tr0WAupgg3I/AAAAAAAAAvg/ezUcgTi0tcs/w1200-h630-p-k-no-nu/java_method.jpg)
&nbsp;
### Variable Types
 - **Local variables** : *Declared in methods, constructors, or blocks*
 - **Instance variables** : *Declared in a class, but outside a method, constructor or any block*
 - **Class/Static variables** : *Declared with the ```static``` keyword in a class, but outside a method, constructor or a block* 

#### Class Variables Example

```java
import java.io.*;
public class Employee {

   // salary  variable is a private static variable
   private static double salary;

   // DEPARTMENT is a constant
   public static final String DEPARTMENT = "Development ";

   public static void main(String args[]) {
      salary = 1000;
      System.out.println(DEPARTMENT + "average salary:" + salary);
   }
}
```
*If the variables are accessed from an outside class, the constant should be accessed as*
```Employee.DEPARTMENT```
### Try this

```java
public class Employee {

   String name;
   int age;
   String designation;
   double salary;

   // This is the constructor of the class Employee
   public Employee(String name) {
      this.name = name;
   }

   // Assign the age of the Employee  to the variable age.
   public void empAge(int empAge) {
      age = empAge;
   }

   /* Assign the designation to the variable designation.*/
   public void empDesignation(String empDesig) {
      designation = empDesig;
   }

   /* Assign the salary to the variable	salary.*/
   public void empSalary(double empSalary) {
      salary = empSalary;
   }

   /* Print the Employee details */
   public void printEmployee() {
      System.out.println("Name:"+ name );
      System.out.println("Age:" + age );
      System.out.println("Designation:" + designation );
      System.out.println("Salary:" + salary);
   }
}

public class EmployeeTest {

   public static void main(String args[]) {
      /* Create two objects using constructor */
      Employee empOne = new Employee("James Smith");
      Employee empTwo = new Employee("Mary Anne");

      // Invoking methods for each object created
      empOne.empAge(26);
      empOne.empDesignation("Senior Software Engineer");
      empOne.empSalary(1000);
      empOne.printEmployee();

      empTwo.empAge(21);
      empTwo.empDesignation("Software Engineer");
      empTwo.empSalary(500);
      empTwo.printEmployee();
   }
}
```
&nbsp;
### Basic Constructs

#### Conditional Statements

```java
if( x < 20 ) {
    System.out.print("This is if statement");
}
```
```java
if( x < 20 ) {
    System.out.print("This is if statement");
}else {
    System.out.print("This is else statement");
}
```
```java
if( x == 10 ) {
    System.out.print("Value of X is 10");
}else if( x == 20 ) {
    System.out.print("Value of X is 20");
}else if( x == 30 ) {
    System.out.print("Value of X is 30");
}else {
    System.out.print("This is else statement");
}
```
```java
if( x == 30 ) {
    if( y == 10 ) {
        System.out.print("X = 30 and Y = 10");
    }
}
```
```java
char grade = 'C';

switch(grade) {
    case 'A' :
        System.out.println("Excellent!"); 
        break;
    case 'B' :
    case 'C' :
        System.out.println("Well done");
        break;
    case 'D' :
        System.out.println("You passed");
    case 'F' :
        System.out.println("Better try again");
        break;
    default :
        System.out.println("Invalid grade");
}
```

#### Repetition

```java
int x = 10;

while( x < 20 ) {
    System.out.print("value of x : " + x );
    x++;
    System.out.print("\n");
}
```
```java
for(int x = 10; x < 20; x = x + 1) {
    System.out.print("value of x : " + x );
    System.out.print("\n");
}
```
```java
String [] names = {"James", "Larry", "Tom", "Lacy"};

for( String name : names ) {
    System.out.print( name );
    System.out.print(",");
}
```
```java
int x = 10;

do {
    System.out.print("value of x : " + x );
    x++;
    System.out.print("\n");
}while( x < 20 );
```

### Arrays
*A fixed-size sequential collection of elements of the same type*

**declaration :**
```java
double[] myList;   // preferred way.
double myList[];   // works but not preferred way.
```
**Initializing**
```
        dataType[] arrayRefVar = new dataType[arraySize];
        dataType[] arrayRefVar = {value0, value1, ..., valuek};
```
```java
double[] myList = new double[10];
double[] myList = {1.9, 2.9, 3.4, 3.5};
```

![java array](https://www.tutorialspoint.com/java/images/java_array.jpg)

```java
public class TestArray {

   public static void main(String[] args) {
      double[] myList = {1.9, 2.9, 3.4, 3.5};

      // Print all the array elements
      for (int i = 0; i < myList.length; i++) {
         System.out.println(myList[i] + " ");
      }
     
      // Summing all elements
      double total = 0;
      for (int i = 0; i < myList.length; i++) {
         total += myList[i];
      }
      System.out.println("Total is " + total);
      
      // Finding the largest element
      double max = myList[0];
      for (int i = 1; i < myList.length; i++) {
         if (myList[i] > max) max = myList[i];
      }
      System.out.println("Max is " + max);  
   }
}
```

### Exceptions
*An exception (or exceptional event) is a problem that arises during the execution of a program*
*An exception can occur for many different reasons. Some are :*
 - A user has entered an invalid data
 - A file that needs to be opened cannot be found
 - Devide by zero

Some built in Exceptions in Java API
 - ArithmeticException
 - ArrayIndexOutOfBoundsException
 - NullPointerException

#### Handling an exceptional event

```java
    int a[] = new int[2];
    try {
        System.out.println("Access element three :" + a[3]);
    }catch(ArrayIndexOutOfBoundsException e) {
        System.out.println("Exception thrown  :" + e);
    }finally {
        a[0] = 6;
        System.out.println("First element value: " + a[0]);
        System.out.println("The finally statement is executed");
    }
```


