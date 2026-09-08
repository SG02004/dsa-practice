# Day 1 — Conditional Thinking in Python

> My Day 1 practice while revisiting Python and preparing for LeetCode.
>
> **Topics:** `if / elif / else`, comparison operators, Boolean logic, `and`, `or`, `not`, nested conditions.

---

## 🟢 Level 1 — Simple Conditions

### 1. Positive, Negative, or Zero

**Problem:** Take a number and print whether it is positive, negative, or zero.

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

**What I practiced:** `if`, `elif`, `else`, and comparison operators.

---

### 2. Even or Odd

**Problem:** Check if a number is even or odd.

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

**Key idea:** If a number has remainder `0` when divided by `2`, it is even.

---

### 3. Divisible by 5

**Problem:** Check if a number is divisible by 5.

```python
number = int(input("Enter a number: "))

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

---

### 4. Divisible by Both 3 and 5

**Problem:** Check if a number is divisible by both 3 and 5.

```python
number = int(input("Enter a number: "))

if number % 3 == 0 and number % 5 == 0:
    print("Divisible by both 3 and 5")
else:
    print("Not divisible by both 3 and 5")
```

**Key idea:** `and` requires both conditions to be `True`.

---

### 5. Leap Year

**Problem:** Take a year and check whether it is a leap year.

A year is a leap year if:
- it is divisible by 400, or
- it is divisible by 4 but not by 100.

```python
year = int(input("Enter a year: "))

if year % 400 == 0:
    print("Leap year")
elif year % 4 == 0 and year % 100 != 0:
    print("Leap year")
else:
    print("Not a leap year")
```

**Key idea:** This is a good example of combining multiple Boolean conditions.

---

### 6. Larger of Two Numbers

**Problem:** Take two numbers and print the larger one.

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))

if a > b:
    print(a)
elif b > a:
    print(b)
else:
    print("Both numbers are equal")
```

---

### 7. Largest of Three Numbers

**Problem:** Take three numbers and print the largest.

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))
c = int(input("Enter the third number: "))

if a >= b and a >= c:
    print("Largest:", a)
elif b >= a and b >= c:
    print("Largest:", b)
else:
    print("Largest:", c)
```

**Key idea:** A number is the largest when it is greater than or equal to both other numbers.

---

### 8. Temperature: Cold, Warm, or Hot

**Problem:** Take a temperature value and classify it as Cold, Warm, or Hot.

I used these ranges:
- below 15 → Cold
- 15 to 29 → Warm
- 30 or above → Hot

```python
temperature = float(input("Enter the temperature: "))

if temperature < 15:
    print("Cold")
elif temperature < 30:
    print("Warm")
else:
    print("Hot")
```

---

### 9. Vowel or Consonant

**Problem:** Take a character and check whether it is a vowel or consonant.

```python
character = input("Enter a character: ").lower()

if character in "aeiou":
    print("Vowel")
else:
    print("Consonant")
```

**Note:** This assumes the input is a single alphabetic character.

---

### 10. Uppercase, Lowercase, Digit, or Special Character

**Problem:** Check whether a character is uppercase, lowercase, a digit, or a special character.

```python
character = input("Enter a character: ")

if character.isupper():
    print("Uppercase")
elif character.islower():
    print("Lowercase")
elif character.isdigit():
    print("Digit")
else:
    print("Special character")
```

**Key idea:** Python strings have useful methods such as `.isupper()`, `.islower()`, and `.isdigit()`.

---

# 🟡 Level 2 — Nested If & Multiple Conditions

## 1. Valid Triangle

**Problem:** Take three sides and check whether they form a valid triangle.

A triangle is valid when the sum of any two sides is greater than the third side.

```python
a = float(input("Enter side 1: "))
b = float(input("Enter side 2: "))
c = float(input("Enter side 3: "))

if a + b > c and a + c > b and b + c > a:
    print("Valid triangle")
else:
    print("Invalid triangle")
```

**Key idea:** All three conditions must be true.

---

## 2. Triangle Type

**Problem:** If the sides form a valid triangle, determine whether it is equilateral, isosceles, or scalene.

```python
a = float(input("Enter side 1: "))
b = float(input("Enter side 2: "))
c = float(input("Enter side 3: "))

if a + b > c and a + c > b and b + c > a:
    if a == b == c:
        print("Equilateral")
    elif a == b or b == c or a == c:
        print("Isosceles")
    else:
        print("Scalene")
else:
    print("Invalid triangle")
```

**Key idea:** The second set of conditions is checked only after the triangle has been proven valid.

---

## 3. Marks and Grade

**Problem:** Take marks from 0–100 and print the corresponding grade.

I used:
- 90–100 → A
- 80–89 → B
- 70–79 → C
- 60–69 → D
- below 60 → F

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 90:
    print("A")
elif marks >= 80:
    print("B")
elif marks >= 70:
    print("C")
elif marks >= 60:
    print("D")
else:
    print("F")
```

**Key idea:** The order of `elif` conditions matters.

---

## 4. Multiple of the Other Number

**Problem:** Check if one of two given numbers is a multiple of the other.

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))

if a == 0 or b == 0:
    if a == 0 and b == 0:
        print("Both numbers are zero")
    else:
        print("Zero is not treated as a multiple here")
elif a % b == 0 or b % a == 0:
    print("One number is a multiple of the other")
else:
    print("Neither number is a multiple of the other")
```

**Key idea:** Check both directions: `a % b` and `b % a`.

---

## 5. Time of Day

**Problem:** Take an hour from 0–23 and print a greeting.

I used:
- 0–5 → Good Night
- 6–11 → Good Morning
- 12–16 → Good Afternoon
- 17–20 → Good Evening
- 21–23 → Good Night

```python
hour = int(input("Enter the hour (0-23): "))

if hour < 0 or hour > 23:
    print("Invalid hour")
elif hour < 6:
    print("Good Night")
elif hour < 12:
    print("Good Morning")
elif hour < 17:
    print("Good Afternoon")
elif hour < 21:
    print("Good Evening")
else:
    print("Good Night")
```

---

## 6. Voting Eligibility

**Problem:** Check voting eligibility for a given age. A person is eligible at age 18 or above.

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible to vote")
```

---

## 7. Even/Odd Combination

**Problem:** Take two numbers and determine whether both are even, both are odd, or one is even and one is odd.

```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))

if a % 2 == 0 and b % 2 == 0:
    print("Both are even")
elif a % 2 != 0 and b % 2 != 0:
    print("Both are odd")
else:
    print("One is even and one is odd")
```

**Key idea:** This combines `and` with comparisons.

---

## 8. Alphabet Range

**Problem:** Take an alphabet character and check whether it lies between `a` and `m` or `n` and `z`.

```python
character = input("Enter an alphabet character: ").lower()

if character >= "a" and character <= "m":
    print("Between a and m")
elif character >= "n" and character <= "z":
    print("Between n and z")
else:
    print("Invalid alphabet character")
```

**Key idea:** Python can compare strings lexicographically.

---

## 9. Day Number

**Problem:** Take a day number from 1–7 and print the corresponding day name.

```python
day = int(input("Enter a day number (1-7): "))

if day == 1:
    print("Monday")
elif day == 2:
    print("Tuesday")
elif day == 3:
    print("Wednesday")
elif day == 4:
    print("Thursday")
elif day == 5:
    print("Friday")
elif day == 6:
    print("Saturday")
elif day == 7:
    print("Sunday")
else:
    print("Invalid day number")
```

---

## 10. Days in a Month

**Problem:** Take a month number from 1–12 and print the number of days in that month. Ignore leap years.

```python
month = int(input("Enter a month number (1-12): "))

if month == 2:
    print("28 days")
elif month in (4, 6, 9, 11):
    print("30 days")
elif month in (1, 3, 5, 7, 8, 10, 12):
    print("31 days")
else:
    print("Invalid month number")
```

**Key idea:** `in` can be used to check whether a value belongs to a collection of values.

---

# What I Learned Today

## 1. `if / elif / else`

I can make decisions in Python:

```python
if condition:
    # runs when condition is True
elif another_condition:
    # runs when the first condition was False
else:
    # runs when all previous conditions were False
```

## 2. Comparison Operators

```text
==    equal to
!=    not equal to
>     greater than
<     less than
>=    greater than or equal to
<=    less than or equal to
```

## 3. Boolean Values

A Boolean can be:

```python
True
False
```

For example:

```python
10 > 5
```

produces:

```python
True
```

## 4. Boolean Operators

### `and`

Both conditions must be true.

```python
age >= 18 and age <= 60
```

### `or`

At least one condition must be true.

```python
day == 6 or day == 7
```

### `not`

Reverses a Boolean value.

```python
not True
```

becomes:

```python
False
```

## 5. The `%` Operator

`%` gives the remainder.

```python
10 % 3
```

gives:

```text
1
```

This is useful for checking divisibility:

```python
number % 5 == 0
```

## 6. Conditions Can Be Combined

For example:

```python
if number % 3 == 0 and number % 5 == 0:
    print("Divisible by both")
```

This is the kind of thinking I will need for LeetCode.

---



# Day 1 Takeaway

The main skill I am building is:

> **Turn a problem statement into conditions that Python can evaluate.**

Instead of immediately thinking about syntax, I should first ask:

1. What are my inputs?
2. What possible cases exist?
3. What condition identifies each case?
4. What should happen in each case?
5. Can I combine conditions using `and`, `or`, or `not`?

This is the foundation I will use as I move from basic Python exercises toward LeetCode problems.

---

## Practice Status

- [x] Level 1 — Simple Conditions
- [x] Level 2 — Nested If & Multiple Conditions
- [x] Reviewed Boolean logic
- [x] Practiced comparison operators
- [x] Practiced `%` for divisibility

**Next focus:** loops (`for`, `while`) and using them together with conditions.
