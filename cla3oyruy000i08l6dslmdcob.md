---
title: "Abstract Classes Vs Interfaces in Java: When to use What?"
seoTitle: "Abstract Classes Vs Interfaces in Java"
datePublished: Sat Nov 05 2022 08:56:41 GMT+0000 (Coordinated Universal Time)
cuid: cla3oyruy000i08l6dslmdcob
slug: abstract-classes-vs-interfaces-in-java-when-to-use-what
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1667638157278/O2QClJ95B.jpeg
tags: java, abstraction, java-programming, 2articles1week, abstract-class-vs-interface

---


Before learning the difference between the two, we must know the meaning of Abstraction.
## **Abstraction**
It simply means hiding unnecessary data about implementation and only showing the functionality to the users.

The most common example of abstraction is a car. The driver knows how to drive the car but does not know how the engine gets designed or how the brakes work. Hence the manufacturer only provides the driver with the general information enough for driving the car and does not disclose the internal mechanism of the car.

Both Abstract Classes and Interfaces are used for Abstraction depending on the scenarios.

## **Abstract Class**
It is a class that is declared with the **‘abstract’** keyword (Abstract means something existing as an idea but not concrete). It may have both 'non-abstract methods' and 'abstract methods'. 
An abstract method does not contain any body but only a method header. It is a method without any implementation. 
Let's discuss the implementation with the help of a code.

```
package com.practiceModule1;

abstract class A{
	public A(){
		System.out.println("This is a constructor of A.");
		}
	public void sing() {
		System.out.println("Let's Sing in...");
	}
    //Abstract Method 
	abstract public void language();
}
//Helper class extending class A
class B extends A{
	@Override
	public void language() {
		System.out.println("Latin");
	}
}

public class MainClass {

	public static void main(String[] args) {
		B b= new B();
		b.sing();
		b.language();
	}

}

``` 
**Output**

```
This is a constructor of A.
Let's Sing in...
Latin
```

When class B extends the abstract class A then we have two options, either make class B abstract or 
override class A's abstract method. 
Using abstract class A, we can create many more useful classes. We can either create more abstract classes using the existing abstract class (class A in this case) or we can create a concrete class like class B by overriding the methods of the abstract class, whose object can be created.
Reference of an abstract class can be created.



## **Interfaces**
An interface is a group of related methods with empty bodies. 
It is sometimes called the blueprint of a class. Java interface can only have abstract methods and variables in it.
If any class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile. **‘Implements’** keyword is used when a class implements an Interface.
Let's get a better understanding of this concept using a code snippet.


```
package com.practiceModule1;
import java.io.*;

interface TV{
	void nextChannel(int increment);
	void prevChannel(int decrement);
}

class Onida implements TV{
	int ch=70;
	@Override
	public void nextChannel(int increment) {
		ch = ch + increment;
	}
	@Override
	public void prevChannel(int decrement) {
		ch = ch - decrement;
		
	}
	public void display() {
        System.out.println("Number:" + ch);
    }
}

public class Interfaces {
    public static void main(String[] args) {
		
        Onida tv = new Onida();
		tv.nextChannel(5);
		System.out.println("Current channel number is:");
        tv.display();
        tv.prevChannel(2);
		System.out.println("Now Current channel number is:");
        tv.display();
        }

}

``` 
**Output**
```
Current channel number is:
Number:75
Now Current channel number is:
Number:73
```

In the example above we can see that Onida class implements the interface TV so all the methods of the interface are implemented by Onida class. We can also observe that both methods are declared as public in the interface because Interface methods are 'public' by default. 
An interface can also extend another interface. 

## **Difference between Abstract Class and Interface**

1.  While Abstract classes can have both Abstract and Non-Abstract Methods, Interfaces can only have abstract methods.

2. Multiple Abstract classes can not be extended but multiple Interfaces can be implemented, supporting multiple inheritance.

3. A sub-class extends the abstract class by using the 'extends' keyword while the 'implements' keyword is used to implement an interface.

## **When to Use What?**
While using the inheritance concept, the abstract class should be used as it provides a common base class implementation to the derived class. Also while declaring private or protected members, abstract class should be used as Interface methods must be public.
For future modifications to the existing base class, an abstract class works better as in the case of interface all the methods have to be implemented by all its derived classes.

Interfaces should be used in places where code doesn't need to be altered for a while.
If multiple inheritances are required, then it can be implemented by using various interfaces.
Interfaces can be used to achieve loose coupling as it provides total abstraction. 

It can be concluded that it depends on the requirements of the project. Both have their own set of pros and cons and both can be used to accomplish similar functionalities. 

I hope you found this article useful. Have a great time! Remember to like, share, and comment with your thoughts.








