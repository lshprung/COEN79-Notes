# Notes from Assignment 0 Videos

## Tenets of OOP - https://www.freecodecamp.org/news/object-oriented-programming-concepts-21bb035f7260/

- Four principles: **encanpsulation**, **abstraction**, **inheritance**, **polymorphism**

### Encapsulation

- When an object has private and public states/functions/methods
- Example: A "Cat" class
	- The class may have private fields, such as mood, hunger, and energy, and a private function `meow()`
	- The class may have three public functions/methods
		- `sleep()` will increase the object's energy and hunger
		- `play()` will increase the object's mood, decrease its energy, and call the private `meow()` function
		- `feed()` will decrease the object's hunger, increase its mood, and call the private `meow()` function

### Abstraction

- Concept that objects should only expose high-level mechanisms
	- Natural extension of Encapsulation concept
- Concept can be seen in real life, for example, a water cooler
	- There is technology going on under the hood, but the end user only sees the lever to pull for water
- Another example: smartphone
	- Very complicated under the hood, but at a high level, there is only the home button, volume buttons, and charge input

### Inheritance

- Idea to combat the problem that often times, many objects are similar but differ slightly
- Involves creating a parent class and a child class, which is derived from the parent
- Example: We can have a Person class with a name and an email
	- Then we can define a Teacher, which has all the fields from the Person class, plus an additional subject field
		- We could create child classes from Teacher for Private Teacher and Public Teacher, which inherit the teacher fields with their own fields as well
	- We could also define a Student, which has all the fields from the Person class, plus additional class and grades fields

### Polymorphism

- Creating a method in a parent that differs slightly between child classes that inherit this method
- Example: There is a Shape parent class that has the method `CalculateArea()`
	- The child classes are Triangle, Circle, and Rectangle, so each child class will have its own implementation of the `CalculateArea()` method

---

## C++ Data Types - https://www.softwaretestinghelp.com/data-types-in-cpp/

- C++ supports two types of data
	- Primitive/Standard data types
	- User-defined data types

### Primitve or Standard Data Types

|Data Type     |C++ Keyword|Value Type                            |
|--------------|-----------|--------------------------------------|
|Character     |char       |Character (ASCII values)              |
|Integer       |int        |Numeric whole numbers                 |
|Floating point|float      |Decimal values with single precision  |
|Decimal point |double     |Double precision floating point values|
|Boolean       |bool       |True or false                         |
|void          |void       |Valueless (no value)                  |
|Wide character|wchar_t    |Character including Unicode strings   |

- Primitves can also be modified in memory length using the following data modifiers:
	- signed
	- unsigned
	- short
	- long

### User-defined Data Types

- **Typedef**
	- Sets an alias for another data type
	- Example:
		- `typedef int age;`
		- The above code creates an alias `age` for the `int` data type

- **Enumeration**
	- Example:
		- `enum daysOfWeek {Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday};`
		- The above code creates a data type `daysOfWeek`. It recognizes all the above keywords (they are really aliases for integer values 0, 1, 2, etc.)
	- Boolean is, in theory, an enumeration, since it recognizes the keywords true and false
	- C++ example:

```
#include <iostream>
using namespace std;

enum daysOfWeek {Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday};

int main(){
	daysOfWeek today;
	today = Thursday;
	cout << "This is day " << today << " of the week";
	return 0;
}

---

//output:
This is day 4 of the week
```

- **Class**
	- Collection of objects
	- Example: a Student class:

```
class student{
	char *name;
	int age;

	public:
		void printDetails(){
			cout << "Name: " << name;
			cout << "Age: " << age;
		}
}
```

- **Structure**
	- A Structure is like a Class, but does not support methods (it can only have variables as its members)
	- A Class is really just a structure that can support both variables and methods
	- Example:

```
struct employee{
	char name[50];
	float salary;
	int empId;
};
```

## What C++ is and Why - https://www.youtube.com/watch?v=tbNe-3FXqFM

### C++ in two lines

- Direct map to hardware
	- of infrastructure and fundamental data types
	- Initially from C
	- Future: use novel hardware better (caches, multicores, GPUs, FPGAs, SIMD, ...)

- Zero-overhead abstraction
	- Classes, inheritance, generic programming, ...
	- Initially from Simula (where it wasn't zero overhead)

### What really matters?

- People
- A programming language is a tool, not an end goal
	- "Ordinary people" want great systems, not programming languages
- Software developers want great tools
	- not just programming language features

### The onion principle

- Management of complexity
	- Make simple things simple!
- Layer of abstraction
	- The more layers you peel off the more you cry

### An engineering approach

- Principled and pragmatic design
- Progress gradually guided by feedback
- There are always many tradeoffs
	- Choosing is hard
- Design decisions have consequences
	- Determine what kind of applications can be done well
