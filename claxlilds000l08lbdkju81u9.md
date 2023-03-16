---
title: "Difference Between throw & throws In Java"
seoTitle: "Difference Between throw & throws In Java"
datePublished: Sat Nov 26 2022 07:13:12 GMT+0000 (Coordinated Universal Time)
cuid: claxlilds000l08lbdkju81u9
slug: difference-between-throw-throws-in-java
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1669445555759/C8Wbcu4J-.png
tags: java, 2articles1week, exceptionhandling, throw, throws

---

Before Understanding the difference between the seemingly similar two terms, we need to understand the concept of exception handling in Java.
Exceptions are unforeseen events that may occur during the execution of the program. It disrupts the normal flow of the program. 
An exception can occur for many reasons. Some of them are:
- Invalid user input
- Device failure
- Loss of network connection
- Physical limitations (out-of-disk memory)
- Code errors
- Opening an unavailable file
An exception can be caught and handled by the program.

![hierarchy-of-java-exceptions.webp](https://cdn.hashnode.com/res/hashnode/image/upload/v1669434975517/FObdyBcvI.webp align="left")
The Throwable class is the superclass of all errors and exceptions in the Java language. Only objects that are instances of this class (or one of its subclasses) are thrown by the Java Virtual Machine or can be thrown by the Java throw statement. 


Both **throw** and **throws** are concepts of exception handling in Java. The **throws** keyword is used to declare which exceptions can be thrown from a method, while the **throw** keyword is used to explicitly throw an exception within a method or block of code by the programmer.
Let's have a look at the program below to get a better understanding.
## Example 1
```
public class exceptionHandling {
	public static void main(String[] args) {
		try{
	         int x = divide(7,0);
	         System.out.println(x);
	     }
	     catch(Exception e){
	         System.out.println("We Got An Exception");
	     }
	}
	private static int divide(int i, int j)throws ArithmeticException {
		int res = i/j;
		 return res;
	}
}
``` 
### Output
```
We Got An Exception
```
In the example above, **throws** keyword is used to declare an exception that can occur while executing the program. The **throws** keyword provides information about the exceptions to the programmer as well as to the caller of the method that throws the exceptions. Here we got this exception because 7 is getting divided by 0.
## Example 2
```
//Unchecked Exception
public class example {
	 public static void divideByZero() {
		    throw new ArithmeticException("Trying to divide by 0");
		  }
	 public static void main(String[] args) {
		 divideByZero();
		}
}
```
### Output
```
Exception in thread "main" java.lang.ArithmeticException: Trying to divide by 0
	at test1/com.practiceModule1.example.divideByZero(example.java:5)
	at test1/com.practiceModule1.example.main(example.java:10)
```
This is an example of an Unchecked Exception. Here, we are explicitly throwing an ArithmeticException. The **throw** keyword is used here to throw an exception. When the divideByZero() method is called, It explicitly **throw** an ArithmeticException.
## Example 3
```
//Checked Exception
import java.io.*;
public class exceptionhandling2 {
	public static void findFile() throws IOException {
	  throw new IOException("File not found Exception");
	}

	public static void main(String[] args) {
		 try {
		      findFile();
		      System.out.println("code in try block");
		    } catch (IOException e) {
		      System.out.println(e);
		    }
      }
}
```
### Output
```
java.io.IOException: File not found Exception
```
This is an example of a checked exception. 
- The main method calls a method findFile() inside a try-catch block.
- Inside the findFile(), it throws an IOException with the message we passed to its constructor. Here the exception has been handled in the main() of the program. 
- Since it is a checked exception, we must specify it in the throws clause. 
- The try...catch block is used to handle exceptions. The program flow execution transfers from the try block to the catch block when an exception is thrown. In the catch block, the exception message gets executed.

### Differences
Here are a few differences between the two terms mentioned in the image below.
![maxresdefault (2).jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1669444947289/o4as5yQ3e.jpg align="left")

## Refrences
- [Scaler.com](https://www.scaler.com/topics/java/)
- [Oracle Java Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
- [Programiz Java Tutorial](https://www.programiz.com/java-programming)
- [JavaTPoint Java Tutorial](https://www.javatpoint.com/java-tutorial)


I hope you found this article useful. Do Like and Share your thoughts in the comment section below.