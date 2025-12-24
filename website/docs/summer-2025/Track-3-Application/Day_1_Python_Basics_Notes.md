# Day 1: Python Tutorial for Beginners Using Thonny

## Introduction to Python

Python is a high-level, interpreted programming language known for its readability and simplicity. It's widely used in various domains such as web development, data analysis, artificial intelligence, scientific computing, and more. Python's syntax is easy to learn, and its code is often more concise compared to other programming languages.

## Setting Up Thonny

Thonny is an integrated development environment (IDE) specifically designed for beginners in Python programming. It comes with a simple interface and provides features that make learning Python easier.

**Installation Steps**:

Just a heads-up: the classroom devices already have the Thonny IDE installed. If you’d like to set it up on your own computer, you can follow these steps to install it.

1. **Download Thonny:**
   - Go to the [Thonny website](https://thonny.org/).
   - Download the version suitable for your operating system (Windows, macOS, or Linux).

2. **Install Thonny:**
   - Run the installer and follow the instructions.
   - Thonny comes with Python built-in, so you don't need to install Python separately.

3. **Open Thonny:**
   - Launch Thonny from your applications menu.
---
## `print()` function: `Hello World`

The first program every programmer writes is a "Hello, World!" program. Let's start with that in Thonny.

1. Open Thonny.
2. In the editor window, type the following code:

```python
print("Hello, World!")
```

3. Save the file with a `.py` extension (e.g., `hello.py`).
4. Run the program by clicking the **Run** button (green arrow) or pressing `F5`.

You should see the output `Hello, World!` in the shell window at the bottom.

**```print()``` function**:
The ```print()``` function is used to output data to the standard output device (screen).

You can print text (strings) by enclosing them in single quotes (```'```) or double quotes (```"```):

```python
print("Bridges to Computing Summer Camp!")
print('Happy to see you!')
print("This is track 3:", "Advanced level track")
```

### Exercise 1: Introduce Yourself

Write a Python program `introduce_yourself.py` that prints an introduction message including:

1. Your name.
2. One sentence about yourself.
3. The reason you are attending this camp.

**Tip:** You will save yourself some trouble during this camp if you get into the habit of organizing your Python files and other related files into a specific folder, named as `camp2025`.

**Example Output**:
```
My name is Bob.
I am a computer science student with a passion for coding.
I am attending this camp to learn more about computer science related skills.
```
---
## Variables and Data Types

Variables are used to store data. In Python, you don't need to declare the type of a variable. Python is dynamically typed, meaning it infers the type based on the value assigned.

**Example**:

```python
# Integer
age = 25

# Float
height = 5.9

# String
name = "Alice"

# Boolean
is_student = True
```

### Data Types

1. Integer: Whole numbers (e.g., `25`)
2. Float: Decimal numbers (e.g., `5.9`)
3. String: Text enclosed in quotes (e.g., `"Alice"`)
4. Boolean: `True` or `False`

### Arithmetic Operators:
Numeric operators are used to perform operations on numbers. Here are the main numeric operators available in Python:
1. ```+``` (Addition)
2. ```-``` (Subtraction)
3. ```*``` (Multiplication)
4. ```/``` (Division)
5. ```%``` (Modulus)
6. ```**``` (Exponentiation)
7. ```//``` (Floor Division)

**Example**:
```python
a = 1
b = 5

print(a + b)  # Output: 15
print(a - b)  # Output: 5
print(a * b)  # Output: 50
print(a / b)  # Output: 2.0
print(a % b)  # Output: 0
print(a ** b) # Output: 100000
print(a // b) # Output: 2
```
### Exercise 2: Calculating Total Camp Hours
You’ll be attending the camp for 5 days. For the first 4 days, you'll stay about 6 hours each day, and on the last day, you'll stay for 4 hours.
Write a Python program to calculate and print the total number of hours you’ll spend at the camp.


---
## Strings and Lists
Strings and lists are fundamental data types in Python. Understanding how to work with them will help you write more complex and powerful Python programs.

In Python, a string is a sequence of characters enclosed within either single quotes (```'```) or double quotes (```"```).

### Creating Strings
You can create a string by assigning a value to a variable:

```python
text = "Hello, World!"
```
### Accessing Characters
You can access individual characters in a string using indexing:
```python
print(text[0])  # Output: H
print(text[7])  # Output: W
```
### Slicing
You can extract a substring from a string using slicing:
```python
print(my_string[1:5])  # Output: ello
print(my_string[:5])   # Output: Hello
print(my_string[7:])   # Output: World!
```
### String Concatenation
You can concatenate two or more strings using the ```+``` operator:
```python
greeting = "Hello"
name = "Bob"
text = greeting + ", " + name + "!"
print(text)  # Output: Hello, Bob!
```

### Lists
A list in Python is a collection of items separated by commas and enclosed within square brackets (```[]```).

### Creating Lists
You can create a list by assigning a sequence of values to a variable:
```python
my_list = [1, 2, 3, 4, 5]
```

### Accessing Elements and Slicing Lists
You can access individual elements in a list using indexings and ou slice a list to extract a sublist, similar to strings:
```python
print(my_list[0])  # Output: 1
print(my_list[2])  # Output: 3

print(my_list[1:4])  # Output: [2, 3, 4]
print(my_list[:3])   # Output: [1, 2, 3]
print(my_list[2:])   # Output: [3, 4, 5]
```

### Functions for Lists
In Python, there are several built-in functions that you can use with lists to perform common operations.
Here are some of the most commonly used functions:

**`len()`**: Get the length of a list.
```python
# example of len()
my_list = [1, 2, 3, 4, 5]
length = len(my_list)
print(length)  # Output: 5
```
**`sum()`**: Sum all elements in a list (works only for numeric lists).
```python
# example of sum()
my_list = [1, 2, 3, 4, 5]
total = sum(my_list)
print(total)  # Output: 15
```

**More functions**
```python
my_list = [1, 2, 3, 4, 5]

# min(): Find the smallest element in a list.
smallest = min(my_list)
print(smallest)  # Output: 3

# max(): Find the largest element in a list.
largest = max(my_list)
print(largest)  # Output: 12

# sorted(): Return a new sorted list from the elements of a list.
my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
sorted_list = sorted(my_list)
print(sorted_list)  # Output: [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]
```
### Exercise 3: Calculate Average Grade

You have a list of grades for a student as below.
```python
# List of grades
grades = [85.1, 90, 92, 88.9, 95]

# add you code below to calculate the average
```
Write a python program `average_grade.py` to calculate the average grade. Print the result.

**Output should be**
```
Average grade: 90.2
```
---

## Control Structures

Control structures allow you to control the flow of your program. The most common ones are if statements and loops (`for` and `while`).

### Comparison Operators:
In Python, comparison operators are used to compare two values. They result in either `True` or `False` based on the comparison result. Here are the main comparison operators in Python:

1. ```==``` (Equal)
2. ```!=```(Not equal)
3. ```> ```(Greater than)
4. ```<``` (Less than)
5. ```>=``` (Greater than or equal to)
6. ```<= ```(Less than or equal to)

**Example**:
```python
a = 10
b = 5

print(a == b)  # Output: False
print(a != b)  # Output: True
print(a > b)   # Output: True
print(a < b)   # Output: False
print(a >= b)  # Output: True
print(a <= b)  # Output: False
```

### `if` Statement:
The if statement allows you to execute a block of code only if a condition is true.

```python
age = 18

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```
You can also have `elif` (else if) statements to check multiple conditions.
```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")

```
### `for` Loop:
The `for` loop is used for iterating over a sequence (e.g., a list, tuple, dictionary, set, or string).

Iterate over a list:
```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```
`while` Loop:
We can also use the `while` loop to iterate over a sequence.
```python
fruits = ["apple", "banana", "cherry"]

i = 0
while i < len(fruits):
    print(fruits[i])
    i =  i + 1
```

### Exercise 4 Identify Numbers

Write a Python program `identify_even.py`, which takes a list of numbers(below) as input to find out the even numbers.

```python
# the list as input
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
**Output should be**
```
Even:
2
4
6
8
10
```
---
## Functions

Functions are reusable blocks of code that perform a specific task.

### Defining a Function:
Use the `def` keyword to define a function.

```python
# define a function
def greet(name):
    print("Hello,", name)

# use (invoke, or call) the function
greet("Bob")  # Output: Hello, Bob
```

### Return Statement:
Functions can return a value using the return statement.
```python
# define a function
def add(a, b):
    s = a + b
    return s

# use (invoke, or call) the function
c = add(1 + 2)
print(c) # Output: 3
```
---
## `input()` function
The `input()` function in Python allows you to take user input from the console. The function reads a line from the input, converts it into a string, and returns it.

### Example 1: Simple Input
```python
name = input("Enter your name: ")
print("Hello,", name)
```
This code will display the message "Enter your name: " and wait for the user to type something. Once the user presses Enter, it captures the input as a string and stores it in the variable name, then prints a greeting.

### Example 2: Converting Input
By default, `input()` returns the entered data as a string. To use the input as a different data type, you need to convert it.
```python
a = int(input("Enter first Integer: "))
b = int(input("Enter second Integer: "))

print("a + b =", a + b)
```
The output will be

```
Enter first Integer: 10
Enter second Integer: 12
a + b = 22
```
### Exercise 4 Process a Sequence of Numbers from Keyboard
Write a Python program named `sequence_input.py` which should implement the following steps:

- Prompt the user to enter numbers one by one.
- Allow the user to specify when they are finished by entering a specific keyword ("done").
- Calculate and print the sum, average, minimum, and maximum of the entered numbers.

**The output of the program should be**
```
Enter a number: 1
Enter a number: 2
Enter a number: 3
Enter a number: 4
Enter a number: done
The sum of the entered numbers is: 10
The average of the entered numbers is: 2.5
The minimum of the entered numbers is: 1
The maximum of the entered numbers is: 4
```

---
## Dice Rolling Simulator Project
Here’s a step-by-step guide to building a simple Dice Rolling Simulator in Python for beginners. This project will help you practice basic programming concepts such as loops, conditionals, functions, and user input.

### Import the `random` module
This module contains the `randint` function which will be used to generate random numbers.
```python
import random
```
### The `randint` method

The `randint` method in Python is part of the  `random` module, and it is used to generate random integers within a specified range.

Here’s how you can use it:
```python
import random

# example 1: Simulating the roll of a six-sided dice, where the possible outcomes are between 1(inclusive) and 6(inclusive).
dice_roll = random.randint(1, 6)
print("You rolled a ", dice_roll)

# example 2: Generating a Random Number Between 10 and 20
random_number = random.randint(10, 20)
print("Random number between 10 and 20: ",random_number)
```

### Basic Dice Rolling Simulator
- Use a loop to repeatedly roll the dice: You can use a while loop to keep rolling the dice until the user decides to stop.
- Generate a random number between 1 and 6: This simulates rolling a six-sided dice.
- Ask the user if they want to roll again: After displaying the result, ask the user if they want to roll the dice again.

Here's the complete code. Copy and paste the code below into your Thonny IDE, then run it.

```python
import random
print("====Welcome====")
signal = 'yes'
# The while True loop ensures the program keeps running until the user decides to stop.
while signal == 'yes':

   # Roll the dice and the result of roll_dice is printed.
   dice_result = random.randint(1, 6)
   print("You rolled a ", dice_result)

   # The user is prompted to decide if they want to roll again. If the user inputs anything other than 'yes', the loop breaks, and the program ends.
   signal = input("Do you want to roll again? (yes/no): ")
   if signal != 'yes':
       print("Thank you for playing!")
```
:bulb: Tip: Use a `while` loop when the number of iterations is not known beforehand and depends on some condition.
Use a `for` loop when you need to iterate over a sequence of elements or a fixed number of iterations.

### Enhance the dice rolling simulator
There are various ways to enhance the dice rolling simulator, providing more interaction and features for the user. Feel free to modify and expand these examples to suit your needs:
- Roll a single die multiple times, keep track of the number of occurrences for each face, and print the results.
- Allow the user to specify the number of sides on the dice.
- Allow the user to specify how many dice they want to roll.
- Additional enhancements?

**Implement your idea using Python.**

Feel free to ask for help if you have any questions.


## References and resources
- [Python Introduction, W3School](https://www.w3schools.com/python/python_intro.asp)
- [The Python Tutorial](https://docs.python.org/3/tutorial/index.html)
- [Python For Beginners](https://www.python.org/about/gettingstarted/)
