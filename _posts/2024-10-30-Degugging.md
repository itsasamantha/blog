# **Debugging: A How To**


### Introduction
If you ever in your life encountered a piece of code more likely than not you're going to have to do some debugging. Debugging is the action of removing errors or **bugs** from a program. This might sound like a hard and tedious task but it's a lot easier than it seems.


This blog post will walk you through the basics of debugging and the types of errors to look out for.


### Number One


Expected Purpose: Determine whether the temperature is hot, temperate, or cold.


``` python
temperature = 75


if temperature > 80:
   print("It's hot")
elif temperature > 50:
   print("It's temperate")
elif temperature < 0:
   print("It's cold")
```


However upon running this code we realize that it would not work if temperature was between 0 and 50. So to fix this we should include a way for numbers 0 to 50 to be considered. To do this we should alter the conditions of the elif statements.


#### **Solution:**
Change the final elif to an **else** statement, this will make sure any temperature less than 50 is determined to be cold.


``` python
temperature = 75


if temperature > 80:
   print("It's hot")
elif temperature > 50:
   print("It's temperate")
else:
   print("It's cold")
```


### Number Two


Expected Purpose: Count how many spaces are in a given string


```python
text = "Hello, world, my name is"
count = 0


for char in text:
   if char == "":
      count += 1


print(count)
```


The problem with this is that the if statement will never be true. It intends to measure the amount of spaces so there should be a space between the quotation marks.


#### **Solution:**


Add a **space** between the quotation marks in the if statement


```python
text = "Hello, world, my name is"
count = 0


for char in text:
   if char == " ":
      count += 1


print(count)
```


### Number Three
Expected Purpose: Determine if numbers 1 to n are even or odd




```python
print("give me a number")
n = input()


for num in range(1, n):
   if num % 2 < 0:
       print(num, "is even.")
   else:
       print(num, "is odd.")
```
For this example the if statement does not separate even and odd numbers.


#### **Solution:**
Change the > to **==** in the if statement


```python
print("give me a number")
n = input()


for num in range(1, n):
   if num % 2 == 0:
       print(num, "is even.")
   else:
       print(num, "is odd.")
```


### Number Four


Expected Purpose: Calculate the factorial of a given number


```python
num = int(input("Enter an integer: "))


if num < -1:
 print("No negative numbers.")
else:
 result = 1
 for i in range(1, num):
   result *= i  


 print("Factorial of " + num + "is" + result)
```


This code segment has multiple issues. Firstly, the if statement does not stop the user from putting in all negative numbers. Second, the for loop does not run the appropriate number of times. Third, the print statement will not concatenate num and result to a string.


#### **Solution:**
The if statement should be changed to **num < 0**:
range should be **(1, num+1)**
the print statement should be formatted with an **f string**






```python
num = int(input("Enter an integer: "))


if num < 0:
 print("No negative numbers.")
else:
 result = 1
 for i in range(1, num+1):
   result *= i  


 print(f"Factorial of {num} is {result}")
```


### Number Five


Expected Purpose: Ask user to enter the correct password but only give them 3 attempts


```python
attempts = 0
correct_password = "secret"


while True:
   password = input("Enter your password: ")
   attempts += 1


   if password == "incorrect_password":
       print("Correct password!")
   else:
       print("Incorrect password")


   if attempts > 3:
       print("Too many attempts")
       break
```




The first if-statement here checks if the password is entered as “incorrect_password” but it should check if it is correct_password(the variable) It also does not stop the loop if the password is correct.


Additionally, The second if-statement’s condition is allowing at least 4 attempts because 3 is not greater than (>) 3.


#### **Solution:**
Change the condition in the first if-statement to **password == correct_password**, so it will check for the right password


Add **break** as the last line in the if before the else. This will stop the for loop.


Change attempts > 3 to be **greater than or equal to 3** so that  it gives the user only 3 chances to get the password right.




```python
attempts = 0
correct_password = "secret"


while True:
   password = input("Enter your password: ")
   attempts += 1


   if password == correct_password:
       print("Correct password!")
       break
   else:
       print("Incorrect password")


   if attempts >= 3:
       print("Too many attempts")
       break
```


## **Congrats you are now a debugging pro!!**
