# Day 2: 🔐 Introduction to CyberSecurity


## Part 1:

### Background
_We’ve discovered that an attacker gained access to a Programmable Logic Controller (PLC) by
exploiting its password. Originally, the PLC password was set to “cool” by the engineer.
However, the attacker changed it and reprogrammed the PLC. As a result, the conveyor belt in
the chocolate factory stopped working correctly. It could no longer sort chocolates with nuts
from those without which a serious problem for customers with nut allergies. If not fixed, the
company could be sued!_


**In this activity, you’ll act as a cyber detective. You’ll examine the communication between
the attacker and the PLC and uncover the new password the attacker set.**

### Activity Materials:
- Download the [Zebra APP](zebra.pcap) and install it.
- Download the [lecture handout](Hands-on_Activity.pdf) and open it.
- Download the [Deer 1 APP](deer_1.pcap) and open it.

## Part 2: Caesar Cipher in Python (For Beginners)

## 🏛️ What Is the Caesar Cipher?

The **Caesar Cipher** is one of the oldest and simplest ways to keep a message secret. It was used over 2,000 years ago by **Julius Caesar**, a Roman general, to send secret messages to his army.

## 💡 Why Learn This?

- It’s fun!
- It teaches how computers **hide information**.
- You’ll write your first **Python program**.

---

## How it works:

- Pick a number (called a **shift**).
- Replace every letter in your message with the letter that comes that many steps **later** in the alphabet.
- If you go past Z, wrap around to the beginning.

📦 Example with a shift of 3:
- A → D
- B → E
- C → F
- ...
- Z → C

So, the message `HELLO` becomes `KHOOR`.

## 🧪 Example

**Original Message:** `HELLO WORLD`


**With a shift of 3:** `KHOOR ZRUOG`

---

## 🧠 Python Basics: `ord()` and `chr()`

### 🔤 Background: How Letters Become Numbers

Computers don’t understand letters the way we do — they understand **numbers**.

Each character you type — like `A`, `B`, or even `!` — has a special number called a **character code**. The most common system is called **ASCII** (American Standard Code for Information Interchange).

Here are some examples:

| Character | ASCII Code |
|-----------|-------------|
| A         | 65          |
| B         | 66          |
| C         | 67          |
| ...       | ...         |
| Z         | 90          |
| a         | 97          |
| b         | 98          |
| c         | 99          |
| ...       | ...         |
| z         | 122         |

To convert letters into numbers and back in Python:

- Use `ord(letter)` → gives you the number
  Example: `ord('A')` → `65`

- Use `chr(number)` → gives you the letter
  Example: `chr(65)` → `'A'`

That’s why in Caesar Cipher, we can shift letters by turning them into numbers, changing the number, then turning them back into letters!


To shift letters, we need a way to turn them into numbers and back.

- `ord('A')` gives the **ASCII** number for a character.
  - Example: `ord('A')` → `65`
- `chr(65)` gives the **character** for a number.
  - Example: `chr(65)` → `'A'`

We use this trick to move letters forward or backward in the alphabet.

### 🧮 Example:
```python
letter = 'B'
number = ord(letter)  # 66
new_number = number + 3  # 69
new_letter = chr(new_number)  # 'E'
print(new_letter)
```
Output is `E`

---

## 👩‍💻 Step-by-Step Python Code

> Don't worry if you’ve never coded before — follow along and copy this code into any Python editor or use an online tool like [https://replit.com](https://replit.com).

### Step 1: Encrypt a Message

```python
def encrypt_caesar(text, shift):
    result = ""
    for char in text:
        shifted = ord(char) + shift
        result += chr(shifted)

    return result

```

### Step 2: Try It Out
```python
message = "Madison"
shift_amount = 3
encrypted = encrypt_caesar(message, shift_amount)
print("Encrypted Message:", encrypted)
```
Output is `Encrypted Message: Pdglvrq`


## 🔓 Decrypt the Message
To reverse the encryption (called decryption), just shift backwards:

```python
def decrypt_caesar(text, shift):
    return encrypt_caesar(text, -shift)
```
### Try Decryption
```python
decrypted = decrypt_caesar(encrypted, shift_amount)
print("Decrypted Message:", decrypted)
```
Output is `Decrypted Message: Madison`

---
### Want More Practices?
Try these challenges to test your skills!

1. 🔄 **Try Different Shifts**
   Change the shift number to 5, 10, or even 25. What happens if you shift by 26?

2. 🆚 **If you move beyond `Z`, you should loop back to the start of the alphabet. That’s why we need apply modulo 26, since there are 26 letters total.**
   Try writing your own sentence and see how it looks when encrypted!

3. 🔡 **Letter Only**
   Modify the code so it processes only letters. What changes will you need to make?
    - Hint: consider using `str.isalpha()` to check if a character is a letter before encrypting it.

4. 🔁 **Wrap-Around Logic**
   What happens if you encrypt the letter `'Z'` with a shift of 1? Does it wrap around to `'A'`?

5. 🕵️‍♀️ **Code Cracker Mode**
   Try to **guess the shift** used to encrypt a message. Can you write code that tries all 26 possibilities?

6. 🧠 **Bonus Challenge**
   Write a function that asks the user for input (with `input()`) and prints the encrypted version.

---
