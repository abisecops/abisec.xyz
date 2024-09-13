---
title: "Why Shouldn’t We Use Var in JavaScript?"
seoTitle: "Avoiding Var in JavaScript"
seoDescription: "Explore why using 'var' in JavaScript may not be ideal due to scope, hoisting, encapsulation, and other issues"
datePublished: Wed Jun 21 2023 20:00:37 GMT+0000 (Coordinated Universal Time)
cuid: cm110i453000t09lbbofz7cnr
slug: why-shouldnt-we-use-var-in-javascript-e32788c258ed
tags: code-review, javascript, websecurity, var-let-const

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726249696295/ca9b4121-1aaf-4de3-99eb-87b22ea08f76.png align="left")

## **Introduction:**

Hey JavaScript fans! Today, we'll explore how to declare variables in JavaScript and why 'var' might not always be the best choice. Let's dive in!

## Difference between Var, Let and Const in JavaScript.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726249698472/ef31ae96-7dc5-40c1-aa5e-40438f066493.jpeg align="left")

╔═════════════╦═════════════════╦════════════════╗  
║ Keyword ║ Scope ║ Reassignment ║  
╠═════════════╬═════════════════╬════════════════╣  
║ var ║ Function scope ║ Allowed ║  
║ let ║ Block scope ║ Allowed ║  
║ const ║ Block scope ║ Not allowed ║  
╚═════════════╩═════════════════╩════════════════╝

## Why Shouldn’t We Use Var in JavaScript?

1. **Function Scope vs. Block Scope:**
    

📝 Note: Variables declared with ‘var’ are function-scoped, meaning they are accessible throughout the entire function, irrespective of the block they are defined in.

```javascript
function myFunction() {
if (true) {
var x = 10;
}
console.log(x); // Output: 10
}
```

**2\. Hoisting:**

📝 Note: Variable declarations using ‘var’ are hoisted, which means they are moved to the top of their scope during compilation. However, only the declaration is hoisted, not the assignment.

```javascript
console.log(myVariable); // Output: undefined
var myVariable = 'Hello!';
```

**3\. Lack of Encapsulation:**

📝 Note: The use of ‘var’ makes it challenging to encapsulate code within modules or functions, as variables are accessible from anywhere within the function.

```javascript
var count = 0;

function incrementCount() {
count++;
}
incrementCount();
console.log(count); // Output: 1
```

**4\. Variable Overriding:**

📝 Note: With ‘var’, redeclaring a variable with the same name within the same scope simply reassigns its value, without throwing an error.

```javascript
var message = 'Hello';

function printMessage() {
var message = 'Hola'; // Variable redeclaration
console.log(message); // Output: Hola
}

printMessage();
```

**5\. No Block-Level Declaration:**

📝 Note: Unlike ‘let’ and ‘const’, ‘var’ lacks block-level scoping, making it harder to manage variables within specific blocks.

```javascript
for (var i = 0; i < 5; i++) {
console.log(i); // Output: 0, 1, 2, 3, 4
}

console.log(i); // Output: 5 (Variable accessible outside the loop)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726249702269/61df6029-b3d3-46c9-b720-f70f2c2e0378.jpeg align="left")

### **Conclusion:**

**Dear coders,**

**Although ‘var’ has its own charm and history, it can sometimes cause confusion and unexpected behavior.**

That’s why, avoid var and adopt let and const in JavaScript. They offer better control, help us organize our code, and make sure everything works smoothly. So, keep coding, keep exploring, and remember to choose your words wisely in JavaScript! Happy coding adventures!