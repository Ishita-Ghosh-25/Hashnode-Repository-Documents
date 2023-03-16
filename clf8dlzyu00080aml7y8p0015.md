---
title: "Understanding the Scope and Scope Chain in JavaScript: A Comprehensive Guide"
seoTitle: "JavaScript Scope and Scope Chain: Complete Guide"
seoDescription: "Learn about JavaScript scope and scope chain in this comprehensive guide. Understand variable accessibility and improve your coding skills"
datePublished: Tue Mar 14 2023 14:56:11 GMT+0000 (Coordinated Universal Time)
cuid: clf8dlzyu00080aml7y8p0015
slug: understanding-the-scope-and-scope-chain-in-javascript-a-comprehensive-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678805471129/432428c8-892f-43fa-9147-eaf8678977d6.png
tags: javascript, javascript-framework, scope, scope-chain

---

JavaScript is one of the most popular programming languages used today, and for good reason. It allows developers to create dynamic and interactive web applications that can be used across multiple platforms. However, to truly master this language, it's important to understand the concept of scope and how it works within the language. In this comprehensive guide, we'll explore the ins and outs of scope and scope chain in JavaScript, giving you the knowledge you need to take your coding skills to the next level.

### What is Scope?

Scope provides a straightforward answer to the question, "Where is the declared variable accessible?"

Scope refers to the part of a program where we can access a variable. It is a space or environment in which a certain variable is declared.

Determining the scope of variables is an essential part of their declaration, as it dictates their accessibility. The environment in which a variable is defined is responsible for establishing its scope.

### Types of Scope

The scope can be classified into three types:

1. **Global Scope**
    
    Variables that are declared outside a function have a global scope i.e. they can be accessed and altered throughout the program.
    
    ```javascript
    let carName = "Hyundai i10"; //carName having a global scope
    //Any code here can use the variable carName
    
    function driveCar(){
    //Any code here can also use the variable carName
    }
    ```
    
2. **Local Scope**
    
    JavaScript function variables have a limited scope and are only accessible and modifiable within the function where they were declared. This is an essential concept to keep in mind when working with JavaScript.
    
    ```javascript
    function myFunction() {
      let carName = "Maruti Suzuki";
      // code here can use carName
    }
    //Any code here can not use carName
    ```
    
3. **Block Scope**
    

Let and const are two essential JavaScript keywords that were introduced in ES6.

In JavaScript, Block Scope is achieved through these two keywords. Any variables declared within a { } block cannot be accessed from outside of that block.

Unlike functions, block statements such as **if** and **switch** conditions, as well as **for** and **while** loops, do not generate a new scope.

```javascript
{
  let x = 2;
}
// x can NOT be used here
```

### Scope Chain

The Scope Chain refers to a situation where a variable with a particular scope (whether global, local to a function or within a code block) is utilized by another variable or function with a different scope (whether global, local to a function or within a code block).

> The Scope Chain refers to the order of scopes that will be explored in order to locate a function or variable.

Let's look at this piece of code first.

```javascript
function sayHello(){
var a = 'a';
return function sayHi(){
    var b = 'b';
    
    return function sayWelcome(){
        var c = 'c';
        console.log(c)
        console.log(b)
        console.log(a)
        return 'Ishita Ghosh'
        }
    }
}

sayHello()()()
```

**Output**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678804435906/62ddc08d-8536-4a6b-a175-e2e80765649a.png align="center")

By doing console.log(a) and console.log(b) we are moving up the scope chain.

JavaScript checks for the value of a variable within its scope and moves upward to the parent scope if it is not found. If the variable is found, JavaScript stores its value where it is being called in a function.

But if we write it this way as mentioned below then we get a reference error.

```javascript
function sayHello(){
var a = 'a';
return function sayHi(){
    var b = 'b';
    console.log(c)
    return function sayWelcome(){
        var c = 'c';
        return 'Ishita Ghosh'
        }
    }
}

sayHello()()()
```

Output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678803730759/e5fc7269-4216-47b1-89dc-88535422dd30.png align="center")

The reason for this is that the variable **c** is declared and defined within the scope of **sayWelcome()**, which means it cannot be accessed outside of that scope.

The Scope Chain comes in handy for resolving variables in JavaScript. When tasked with resolving a variable, JavaScript begins its search at the deepest level of the code nest and continuously jumps up to the parent scope until it locates the variable or any other resource it requires.

### Conclusion

In conclusion, understanding scope and scope chain in JavaScript is crucial for any developer looking to master this language. By grasping the concept of scope, you can ensure that your variables are accessible where you need them to be, and by understanding the scope chain, you can resolve variables and resources effectively. With this comprehensive guide, you now have the knowledge you need to take your coding skills to the next level and create dynamic and interactive web applications with confidence.

Thank you for taking the time to read this article. I hope you found it interesting and informative. If you have any questions or suggestions, please feel free to leave them in the comments section. Your feedback is valuable.