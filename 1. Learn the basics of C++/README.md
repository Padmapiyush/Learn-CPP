# Basics of C++

> *C++ is a case-sensitive language, which means that uppercase and lowercase letters are considered different. The syntax of C++ consists of various elements, including keywords, operators, comments, and identifiers.*

## Keywords:
Keywords are reserved words in C++ that have a specific meaning and cannot be used as identifiers. Some examples of C++ keywords include:

* int (for declaring integer variables)
* double (for declaring double-precision floating-point variables)
* if (for conditional statements)
* else (for alternative conditional statements)
* while (for loops)
* for (for loops)
* switch (for selecting among multiple alternatives)

## Operators:
Operators are symbols that perform specific operations on one or more operands. Some examples of C++ operators include:
```cpp
+ (addition)
- (subtraction)
* (multiplication)
/ (division)
% (modulus)
++ (increment)
-- (decrement)
== (equality)
!= (not equal)
< (greater than)
< (less than)
>= (greater than or equal to)
<= (less than or equal to)
&& (logical AND)
|| (logical OR)
! (logical NOT)
```
## Comments:
Comments are used to add explanations or notes to the code. In C++, comments can be either single-line or multi-line. Single-line comments start with //, while multi-line comments start with /* and end with */.

## Identifiers:
Identifiers are names given to variables, functions, and other elements in C++. Identifiers must follow certain rules, such as starting with a letter or underscore and not containing spaces.

## Data types:
C++ supports several data types, including:

* int (for integer values)
* double (for floating-point values)
* char (for single characters)
* bool (for boolean values, which can be true or false)
* string (for sequences of characters)

## Variables:
Variables are used to store values in C++. To declare a variable, you must specify its data type and give it a name. For example, to declare an integer variable called x, you would write:

```cpp
int x;
```

## 1. Conditional Statements:
Conditional statements are used to execute code based on a certain condition. The most common conditional statement in C++ is the if statement, which allows you to execute a block of code if a certain condition is true. Here's the basic syntax of an if statement:

```c++
if (condition) {
  // code to be executed if condition is true
}
```
You can also use an else statement to execute a different block of code if the condition is false:

```c++
if (condition) {
  // code to be executed if condition is true
} else {
  // code to be executed if condition is false
}
```
You can also use else if statements to check multiple conditions:

```c++
if (condition1) {
  // code to be executed if condition1 is true
} else if (condition2) {
  // code to be executed if condition2 is true and condition1 is false
} else {
  // code to be executed if both condition1 and condition2 are false
}
```

## 2. Switch Statements
Switch statements allow you to execute different blocks of code based on the value of a variable. The basic syntax of the switch statement is:

```c++
switch (variable) {
   case value1:
      // code to execute if variable equals value1
      break;
   case value2:
      // code to execute if variable equals value2
      break;
   // add more cases as needed
   default:
      // code to execute if variable does not match any of the cases
      break;
}
```
Note that each case should end with a break statement to prevent execution from falling through to the next case.

## 3. Loops:
Loops are used to repeat a block of code a certain number of times, or until a certain condition is met. There are three main types of loops in C++: while loops, for loops, and do-while loops.

### While Loops:
A while loop is used to repeat a block of code while a certain condition is true. Here's the basic syntax of a while loop:

```c++
while (condition) {
  // code to be executed while condition is true
}
```

### For Loops:
A for loop is used to repeat a block of code a certain number of times. Here's the basic syntax of a for loop:

```c++
for (initialization; condition; update) {
  // code to be executed while condition is true
}
```
The initialization step is used to set the initial value of the loop variable, the condition is used to determine when to exit the loop, and the update step is used to modify the loop variable after each iteration.

### Do-While Loops:
A do-while loop is used to repeat a block of code at least once, and then continue repeating it while a certain condition is true. Here's the basic syntax of a do-while loop:

```c++
do {
  // code to be executed at least once
} while (condition);
```

## Jump Statements:
Jump statements are used to transfer control to a different part of the program. The two main jump statements in C++ are break and continue.

### 1. Break:
The break statement is used to exit a loop prematurely. When the break statement is encountered inside a loop, the loop is immediately terminated and program control jumps to the next statement after the loop. Here's an example of using the break statement inside a for loop:

```c++
for (int i = 0; i < 10; i++) {
  if (i == 5) {
    break;
  }
  // code to be executed while i is less than 5
}
```

In this example, the loop will terminate when i equals 5, and the program will continue executing after the loop.

### 2. Continue:
The continue statement is used to skip the current iteration of a loop and continue with the next iteration. When the continue statement is encountered inside a loop, the program skips any remaining code inside the loop for the current iteration and jumps to the next iteration. 

```cpp
for (int i = 0; i < 10; i++) {
   if (i == 5) {
      continue; // skip over this iteration and move on to the next one
   }
   // code to execute while loop is running
}
```

In this example, when the condition inside the loop block is true, the program will execute the first set of statements, and then check the value of someCondition. If someCondition is true, the program will skip over the remaining statements for the current iteration, and move on to the next one.

### 3. goto:
The goto statement is used to transfer control to a labeled statement within the same function. The labeled statement must be defined within the same block, or within a block nested inside the current block.

```cpp
int i = 0;
label1:
i++;
if (i < 10) {
    goto label1;
}
```
In this example, the program uses a goto statement to jump to the label1 statement whenever the condition i < 10 is true. This creates a loop that will run 10 times.

> Note that the use of goto statements is generally discouraged in modern programming, as it can make code difficult to read and understand. In most cases, the break and continue statements can be used instead to achieve the desired control flow.













