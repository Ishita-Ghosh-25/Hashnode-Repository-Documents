---
title: "Understanding Access Modifiers In C++"
seoTitle: "Access Modifiers In C++"
datePublished: Mon Dec 05 2022 12:18:27 GMT+0000 (Coordinated Universal Time)
cuid: clbardtaj000o08l489nk84z1
slug: understanding-access-modifiers-in-c
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1670242577551/8JOTA9su6.png
tags: cpp, programming-blogs, beginners, cpp-guide, access-modifiers

---

Let us try to understand some important keywords in C++, which are `public, private, and protected.` These things are beneficial while building large applications and help to provide a better understanding of object-oriented programming concepts.

One of the primary characteristics of object-oriented programming languages such as C++ is **data hiding**. They are also widely used in the case of inheritance.

## What are Access Modifiers?

Access Modifiers or Access Specifiers are used to determine the range of use of variables and functions of any class. These are keywords used to specify the accessibility of a class and its members. These modifiers can be used from code inside or outside the current application.

## Types Of Access Modifiers in C++

In C++, there are three types of Access Modifiers

1.  Public
    
2.  Private
    
3.  Protected
    

Let's start with understanding each one of them with an example.

### Public

*   The `public` keyword is used to create public data members and functions.
    
*   The public members are accessible from any part of the program.
    
*   The data members and member functions declared as public can be accessed by other classes and functions too.
    
*   The public members of a class can be accessed from anywhere in the program using the **(.)** with the object of that class.
    

**Code**

```cpp
#include<iostream>
using namespace std;
//Class Definition
class Rectangle
{
	public:
		int length, breadth;
		int computeArea()
		{
			return length*breadth;
		}
	
};

// main function
int main()
{
	Rectangle obj;
	// accessing public datamember outside class
	obj.length = 5;
    obj.breadth = 3;
	
	cout << "Length is: " << obj.length << "\n";
    cout << "Breadth is: " << obj.breadth << "\n";
	cout << "Area is: " << obj.computeArea();
	return 0;
}
```

**Output**

```cpp
Length is: 5
Breadth is: 3
Area is: 15
```

In the above program, the data member *length* and *breadth* are declared as public so they could be accessed outside the class and therefore were permitted access from inside the main() function. 

### Private

*   The `private` keyword is used to create private data members and functions.
    
*   The private members can only be accessed from within the class.
    
*   They are not allowed to be accessed directly by any object or function outside the class.
    
*   However, friend classes and friend functions can access private members.
    
*   We can use the keyword `friend` to ensure the compiler understands and make the data accessible to that function.
    

**Code**

```cpp
#include<iostream>
using namespace std;
//Class Definition
class Rectangle
{
	private:
		int length, breadth;
    public:
		int computeArea(int length, int breadth)
		{
	        int area = length*breadth;
	        cout << "Length is: " << length << "\n";
            cout << "Breadth is: " << breadth << "\n";
            cout << "Area is: " << area << "\n";
		}
};
// main function
int main()
{
	Rectangle obj;
    obj.computeArea(5,3);
	return 0;
}
```

**Output**

```cpp
Length is: 5
Breadth is: 3
Area is: 15
```

Here the main() can not directly access class variable *length* and *breadth*. We can only make changes indirectly through the function computeArea(), since this function initializes length and breadth with the value of the argument passed to it i.e. the function parameter `int length & int breadth`

### Protected

*   The `protected` keyword is used to create protected data members and functions.
    
*   The protected members can be accessed within the class and from the derived class or subclasses as well.
    

**Code**

```cpp
#include<iostream>
using namespace std;
//Class Definition
class Rectangle
{
	protected:
		int length, breadth;
};
// Declaring a child Class
class Area : public Rectangle{
    public:
        int computeArea(int length, int breadth)
		{
	        int area = length*breadth;
	        cout << "Length is: " << length << "\n";
            cout << "Breadth is: " << breadth << "\n";
            cout << "Area is: " << area << "\n";
		}
};
// main function
int main()
{
	Area obj;
    obj.computeArea(5,3);
	return 0;
}
```

**Output**

```cpp
Length is: 5
Breadth is: 3
Area is: 15
```

Here, `Area` is an inherited class that is derived from `Rectangle`. The variable *length* and *breadth* are declared in `Rectangle` with the `protected` keyword.

This means that `Area` can access variable *length* and *breadth* since `Rectangle` is its parent class.

### Analogy

> Lets consider a real-life example of Public access modifier. The roads and street light are accessible to anyone and everyone. No rectrictions are applied on their usage throught the city.
> 
> While your mobile phone resembles Private access modifier. Only you can have its access.
> 
> Your property and your assets are like Protected access modifier. You can use them and your children can inherit them from you.

### Differences Between the 3 terms

| Public | Private | Protected |
| --- | --- | --- |
| Can be inherited. | Can not be inherited. | Can be inherited |
| Members are accessible from outside the class | Members cannot be accessed (or viewed) from outside the class | Members cannot be accessed from outside the class, however, they can be accessed in inherited classes |

## Conclusion

I hope by now you have gained a clear understanding how accesses modifiers work in C++. I am grateful for the time you have invested in reading this. I hope you enjoyed reading my article. Do like, share and comment your thoughts in the comment section below.

## References

1.  [Programiz](https://www.programiz.com/cpp-programming)
    
2.  [W3School](https://www.w3schools.com/cpp/cpp_access_specifiers.asp#:~:text=In%20C%2B%2B%2C%20there%20are,be%20accessed%20in%20inherited%20classes.)
    
3.  [GeeksForGeeks](https://www.geeksforgeeks.org/access-modifiers-in-c/)