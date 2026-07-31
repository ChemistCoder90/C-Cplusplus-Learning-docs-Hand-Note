<div align="center">

# 📘 C++ Hand Notes

### *"C++: 31 hours long video of freecodecamp"*

![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![FreeCodeCamp](https://img.shields.io/badge/FreeCodeCamp-0A0A23?style=for-the-badge&logo=freecodecamp&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active_Notes-brightgreen?style=for-the-badge)

</div>

---

## 📑 Table of Contents

| # | Topic |
|---|-------|
| 01 | [Statement & Variable](#statement--variable) |
| 02 | [Number System & Data Types](#number-system--data-types) |
| 03 | [Float and Double](#float-and-double) |
| 04 | [Boolean & Character](#boolean--character) |
| 05 | [Operators & Manipulators](#operators--manipulators) |
| 06 | [Flow Control & Arrays](#flow-control--arrays) |
| 07 | [Static Variable](#static-variable) |
| 08 | [Enum](#enum) |
| 09 | [Pointer](#pointer) |
| 10 | [Memory Map](#memory-map) |
| 11 | [Dynamic Memory Allocation](#dynamic-memory-allocation) |
| 12 | [NULL Pointer Safety & Memory Leaks](#null-pointer-safety) |
| 13 | [Dynamic Array & Reference](#dynamic-array--reference) |
| 14 | [String & Character Array](#string--character-array) |
| 15 | [Functions & Function Overloading](#functions) |
| 16 | [Lambda Function](#lambda-function) |
| 17 | [Function Template](#function-template) |
| 18 | [Template Specialization](#template-specialization) |
| 19 | [C++ 20 — Concepts](#c-20) |
| 20 | [Type Traits](#type-traits) |
| 21 | [Custom Concepts & Requires](#build-own-conceptcustom-concept) |
| 22 | [OOP — Class & Object](#oop) |
| 23 | [Constructor, Setter & Getter](#constructor) |
| 24 | [Pointer in Class & Destructor](#manage-class-object-by-pointer) |
| 25 | [this Pointer, Struct, Size](#this-pointer) |
| 26 | [Inheritance](#inheritance) |
| 27 | [Constructors with Inheritance](#default-arc-constructor-with-inheritance) |
| 28 | [Copy Constructor](#copy-constructors-with-inheritance) |
| 29 | [Inheriting Base Constructor](#inheriting-base-constructor) |

---

**“C++: 31 hours long video of freecodecamp”**

***Didn’t add basics Like: if,else; Loop,Function, Switch etc.

Features: 

Supports data abstruction, means Data abstraction is a fundamental concept in computer science and software engineering that involves hiding the implementation details of data types and exposing only the essential features or behaviour to the outside world. Data abstraction is a powerful concept that facilitates the design, implementation, and maintenance of complex software systems by providing clear interfaces, encapsulating implementation details, promoting modularity, and supporting information hiding.

---

Statement: A statement is a basic unit of computation in a C++ program. Ends with a semicolon(;).

	They are executed from top to bottom when program is run. 

---

![image-001.png](images/image-001.png)

  
---

input For Space separated word 

![image-002.png](images/image-002.png)

   
**Variable:** A piece of memory that used to store specific type of data.

**Number System representation:**

![image-003.png](images/image-003.png)

> Modifier like signed, unsigned used integral data type as decimal number/ whole number. Can’t use for float, double(2.0, 2.5).

**Float and Double:**

![image-004.png](images/image-004.png)

 

***Precision includes digits before decimal point(.). 12547.325-> 12547 included in the precision.

For Float: 12345.6789-> 89will be garbage value. Cause precision 7 for Float. May print like: 12345.6725

> float a=123456789-> 89 will b garbage value. May print like: 12345.6745

![image-005.png](images/image-005.png)

 
   
Floating point number memory representation is not similar to decimal number. It explained in IEEE_754 -> IEEE_754-> Press ctrl & Click

![image-006.png](images/image-006.png)

![image-007.png](images/image-007.png)

 
```cpp
cout<<setprecision(20);
```

![image-008.png](images/image-008.png)

If we not set precision, the default precision will be 6 digits.(Total digits. Not after decimal point)

if we use **“fixed” **the with set precision(4), precision will be 4 after decimal point. Above a=12.1234;(ans)

But not using “fixed” precision will be 4 for total digits. Above a=12.12;(ans)

used for set precision. Library> `#include<iomanip>`

**suffixes(like f, L):** u // unsigned

ul // unsigned long

ll // long long

---

****Booleans** occupy **1byte/8bits** in memory.

```cpp
bool x=true; // or bool x=1;
bool y=false; // or bool y=0;
```

**cout<<boolalpha;** **//used for printf true/false ****instead of 0/1**

```cpp
cout<<x<<” ”<<y;
```

will print true, false.

---

**Character:**

![image-009.png](images/image-009.png)

![image-010.png](images/image-010.png)

 

![image-011.png](images/image-011.png)

---

> 31/10 means how many times 10 is gonna fit in 31. so ans is 3.

* Relation Operator: > ,< , >=, <=

* Logical Operator: &&, ||, !

---

**Manipulator:    https://en.cppreference.com/w/cpp/io/manip   //for more**

**std:flush: **when we print something, it does not go directly to the terminal. It store somewhere called “buffer”. When buffer is full/ complete it goes to terminal. If use std:flush data directly goes to console/terminal instead of goes to buffer.

![image-012.png](images/image-012.png)

*************setw() :** set width

```cpp
cout<<right; // printf from right. 	Left for left alignment
```

![image-013.png](images/image-013.png)

```cpp
cout<<setfill(‘-’) // blank space fill with ‘-’
```

![image-014.png](images/image-014.png)

  

*for finding max min numeric number limits data type can hold.

Need this> `#include<limits>` 

https://en.cppreference.com/w/cpp/types/numeric_limits

![image-015.png](images/image-015.png)

  

---

```cpp
#include<cmath> : abs(), pow(),  ceil(), log(), sqrt(), sin(), tan() etc
```

 https://en.cppreference.com/w/cpp/header/cmath 

for log(): log(10) means loge(10). So have to fix the base as log10(10). E=2.71..

* round(): 3.5 will make 4, and 3.49 will make 3.

---

![image-016.png](images/image-016.png)

  
if we take data type less than 4 byte and perform arithmatic operation compiler automatically convert it to 4 byte. This behavior also present on other operator like bitwise operator.(>>, <<) 

---

flow control: if else, switch, ternary operator.

***Switch: if we not use “Break”, the case which match, after that all case will execute and print every case value.**

*** we can use int, char , double, enum etc but not string as case.**

---

* If we use “const” before array. We cant modify array elements.

*** a[ ]={2,3,7,5,2,3}; size(a) return the size of array. /Or sizeof(a)/sizeof(a[0]);**

---

**Static Variable****: **A static variable initialize only once and retains its value between function calls / across different scopes, instead of being destroyed and recreated each time.

![image-017.png](images/image-017.png)

- is created **only once**

- exists for the **entire lifetime of the program**

- is **not destroyed** when it goes out of scope

---

**Static Global Variable: **As we know global variables are accessible from other .cpp file. In case of static global declaration, the variable is only visible within that translation unit (source file), not to other .cpp files.

![image-018.png](images/image-018.png)

 

---

**Enum: **An ****enum**** is a special type that represents a group of constants (unchangeable values).

To create an enum, use the enum keyword, followed by the name of the enum, and separate the enum items with a comma.

![image-019.png](images/image-019.png)

Enum is short for "enumerations", which means "specifically listed".

To access the enum, you must create a variable of it.

**Inside the main() method, specify the enum keyword, followed by the name of the enum (Level) and then the name of the enum variable (myVar in this example):**

![image-020.png](images/image-020.png)

**By default, the first item (LOW) has the value 0, the second (MEDIUM) has the value 1, etc.**

If you now try to print myVar, it will output 1, which represents MEDIUM:

![image-021.png](images/image-021.png)

As you know, the first item of an enum has the value 0. The second has the value 1, and so on. To make more sense of the values, you can easily change them:

![image-022.png](images/image-022.png)

***Note that if you assign a value to one specific item, the next items will update their numbers accordingly:

![image-023.png](images/image-023.png)

**Example:**

![image-024.png](images/image-024.png)

#### Why And When To Use Enums?

Enums are used to give names to constants, which makes the code easier to read and maintain. Use enums when you have values that you know aren't going to change, like month days, days, colours, deck of cards, etc.

---

**Pointer**

Pointer is special kind of variable.

```cpp
int* int_num{}; or int* int_num; // will point to a integer type variable //initialise with null 					     // pointer(nulptr)
double* frac_num{}; // will point to a double type variable
int * int_num{}; // this initialisation with {} is going to initialise with special address means it is not 			//pointing any variable. Means initialize  with **nullptr**
int * int_num{nullptr}; // this pointer not pointer anywhere
```

> pointer of int, double, char etc all are same size. Cause they only store address.

**Char *ptr{“Hello world”}; **// Pointer will point to 1st character. Some compiler will not compile(MSVC). GCC will give warning and compile. A whole string is assigning to char type pointer. **See:10:17:00**

Cout<<ptr; // will print whole string.

```cpp
Cout<<*ptr;// print 1st character ‘H’;
```

*ptr=’B’;// this may give error. Cause compiler will think it as const char array.

 If want to modify. Don’t use character pointer, use array like: **char msg[10]==”Hello world”;**

or use **const char *ptr{“Hello world”};**  // no warning. Can’t modify also.

**Dereferencing pointer: reading something(value) on the address of the pointer. Cout<<*ptr;**

```cpp
string with pointer: char* p_msg= “Hello World!”; // the pointer will point to the 1st character of string
```

***this will compile with warning. Use const char* p_msg= “Hello World!”;**

**printf p_msg will print whole string. But using dereferencing will print 1st character(*p_msg).**

> without const it gives warning/refuse to compile cause compiler is going to convert string into char array of constant char. What we are using is points to that is not a const char pointer. So pointer here might be used to try or modify data. That’s why it refuse unless using const.

Check at 10:17min

```cpp
int *ptr;// contain junk address
int a=12;
*ptr=&a;
```

uninitialized pointer contain junk address. Assigning a value to it(*ptr=12)May cause error. Could be point to a memory which is used by OS. May cause disaster. 

Use this: int a; int *ptr=&a;

![image-025.png](images/image-025.png)

 

**Memory Map**

When we run a program it runs on RAM. Various program of OS or other is running on memory.

![image-026.png](images/image-026.png)

 

![image-027.png](images/image-027.png)

  

This process thinks it own 0~2N  (2 pow N)amount of memory which is virtual memory.

When we run a program it is going to go through a CPU section called memory management unit(MMU).

![image-028.png](images/image-028.png)

 
Part that are likely not to be used are discarded from the RAM.

MMU really does is, helps us mapping between the memory map in ur program and the real thing we have in RAM.

If we run few program, they are going to go through MMU and MMU is going assign them real section on RAM

![image-029.png](images/image-029.png)

* Since program thinks it 2n -1 memory, The MMU is going to transform between the idea the program has and the RAM we have(assigned memory by MMU).

* The memory map/Structure of program is standard format defined by OS. That’s why we can’t run directly window program on Linux.

*Memory map is divided into a lot parts

![image-030.png](images/image-030.png)

* **STACK: **Local variable stores on stack section.

	* print, statement, function calls others store on stack section.

* **TEXT:**Actual binary load on Text so that CPU can execute it.

* **HEAP:**Additional memory when we run out of stack memory also to  make things better for program, Used for run time.

---

**Dynamic Memory Allocation**

![image-031.png](images/image-031.png)

 
**2nd point- full Control:  when declare a variable a=23; in stack it remove when scope is over. Developer doesn’t have full control. But in heap developer have full control when a variable comes to work and dies.**

**>> 10:41 min**

![image-032.png](images/image-032.png)

  

***set up a pointer which point to heap memory.**

**After initializing a pointer with nullptr. When p_number4=new int execute the OS is allocate a memory on heap. Variables are usually stores on stack section. It removes when variable containing scope will over. But if we allocate a memory on heap by “p_number4=new int;” . This memory will live though its scope is over. It will stay until return it to operating system. To return:**

![image-033.png](images/image-033.png)

 

Use ‘delete’ to return memory to the  operating system. After return reset pointer to ‘nullptr’ is good to make it clear that no valid data pointer is pointing.

* Using ‘delete’ remove the allocated heap memory which is pointed. Not the pointer. If pointing to ‘nullptr’, delete will do nothing.

> Always remember to release memory.

---

**Dangling Pointer:** A pointer that doesn’t point to a valid memory address. Trying to dereferencing and using a dangling pointer  will results in undefined behaviour. 

How dangling pointer create:

1. Uninitialized pointer.

2. Delete pointer

3. Multiple pointer points to same memory.

Solution:

1. Initialize pointer. Either with valid address or nullptr.

2. Reset pointer after delete.(Either with valid address or nullptr.)

3. For multiple pointer point to same address, make sure master pointer is clear/ reset.

> Always check if pointer is nullptr or not by if-else.

---

**‘New’ fails:**

When allocating an array with pointer with huge size(1000000000000000000). It may fails and program can crash. We can use **exception mechanism or ‘nothrow’** to prevent crashing.

![image-034.png](images/image-034.png)

 

Both allocation (with for loop or without) fail.

*** Solve with ‘exception mechanism’:**

![image-035.png](images/image-035.png)

 

With ‘exception’ we can catch the problem. What is called ‘handle’ in the problem. Suppose we are going to set up color and color fails. UI(interface) may show black and white. But program will keep running **“****what()****” ** function will show the error.

***with ‘nothrow’: **If “new” fails, we are going to get “nullptr” stored.

![image-036.png](images/image-036.png)

 

For clear understanding see 

https://www.youtube.com/watch?v=uoCuMTzD9AE&list=PLgH5QX0i9K3q0ZKeXtF--CZ0PdH1sSbYL&index=90 // anisul islam lecture 92. Exception handling

---

**NULL pointer safety:**

![image-037.png](images/image-037.png)

 

check if null or not.

![image-038.png](images/image-038.png)

 
Or,

![image-039.png](images/image-039.png)

 
Pointer address implicitly converted into boolean. (null==0).

> After use delete set pointer to nullptr for safety.

---

**Memory Leaks:**

![image-040.png](images/image-040.png)

   

![image-041.png](images/image-041.png)

 

while 2nd allocation, pointer changes its pointing location to 2nd memory. Don’t have access of 1st memory(55).

Should delete 1st then allocate 2nd.

![image-042.png](images/image-042.png)

 

After local scope is over, pointer is gonna die, but allocated memory will remain and loose access.

These memory leaks may causes program crash.

---

**Dynamic array: Array stores on the heap.**

![image-043.png](images/image-043.png)

  

![image-044.png](images/image-044.png)

  

Release Memory:

![image-045.png](images/image-045.png)

Dynamic arrays are created at run time not compile time.

 

![image-046.png](images/image-046.png)

 

Explanation:

![image-047.png](images/image-047.png)

  

![image-048.png](images/image-048.png)

 

---

**Reference: **A **reference** is an **alias** (another name) for an existing variable. It **does not create a new variable or ****occupy ****memory**, it just gives another way to access the same memory. Doesn’t hold addresses as pointer.

 

![image-049.png](images/image-049.png)

```cpp
int x = 10;
int& ref = x;
```

![image-050.png](images/image-050.png)

If we change reference value or variable value, both contribute same changes.

*********** “&ref” and “&s” both has same memory address.

![image-051.png](images/image-051.png)

  

![image-052.png](images/image-052.png)

 

Reassign a Pointer  to others variable, but reference can’t.

![image-053.png](images/image-053.png)

 

Here ‘S and ref’ value will changes to 12.

**Use case: *if want to modify original variable inside a function. This save memories.**

![image-054.png](images/image-054.png)

 

* Return reference by function to a local or global variable.

 

![image-055.png](images/image-055.png)

![image-056.png](images/image-056.png)

 

* Using “const” before reference makes the variable unchangeable. This constant only applies to reference. Not variable. Can’t changes variable value with “const reference”. But variable itself can changes its value.

![image-057.png](images/image-057.png)

 

Value will changes to 12.

---

> size(), sizeof() function return the size. But for character array it includes ‘null’ . But for string  size() don’t count null.

> strlen() is used for character array. Not for string.

```cpp
		char *a=”asdf”;     // this is string literal. Not modifiable.
```

		Char a[]=”asdf”;   // this is character array. Modifiable. Use stack memory.

Using “const” is safe in string literal.

***String literal is actually a character array. When we assign it to “const char * ”, it automatically converts into a pointer to 1st element. String has not fixed amount of memory, cause it internally implemented as a class and it stores its data as **const char pointer.**

```cpp
		Const char *msg=”Hello I am here.”;
```

![image-058.png](images/image-058.png)

Character array lives on read only memory. Can’t modify.

---

swap 2 number.

```cpp
1. a=a+b;     b=a-b;    a=a-b;
2. a=a^b;      b=a^b;   a=a^b;
```

---

**Returning from function as Reference: Usually function returns values(int, char etc). But sometime compilers are smart enough that that return reference instead of values. Avoid copies. See below**

![image-059.png](images/image-059.png)

Example:

![image-060.png](images/image-060.png)

   

Output:

![image-061.png](images/image-061.png)

Here both addresses are same. Its returns the reference. Using reference mechanism.

---

**Function Overloading**

**Function Overloading: Means we can declare multiple function with same name in the same scope, but with different parameter lists. Like parameter type(int, double, float).**

Below All allowed.

![image-062.png](images/image-062.png)

![image-063.png](images/image-063.png)

![image-064.png](images/image-064.png)

Not allowed.(below)

![image-065.png](images/image-065.png)

 

![image-066.png](images/image-066.png)

 

---

![image-067.png](images/image-067.png)

When **‘int’** type variable is passed as argument “int overload will called”. Same as double and others.

---

**lambda Function:**

![image-068.png](images/image-068.png)

     

![image-069.png](images/image-069.png)

* Return type is not important. If keep blank, compiler is gonna deduce its type by itself.

* Use ‘;’ after function body. Because lambda function is a statement.

![image-070.png](images/image-070.png)

 

![image-071.png](images/image-071.png)

   

![image-072.png](images/image-072.png)

 

Here  if lambda function return something, it going to assign to variable ‘fun’.

---

**Capture lists on lambda function: Capture list is a part of lambda function inside the square brackets which tells the lambda function, which variable from the surrounding scope it can use and how(like using a copy of a variable or references).**

* When a lambda function capture values, it made a copy of that variable on the memory. So if that variable is changed later it will not effect on that lambda function. Lambda function retain the old value unless we use variable as reference. See below…

![image-073.png](images/image-073.png)

 

![image-074.png](images/image-074.png)

See when we use variable as reference:

![image-075.png](images/image-075.png)

 

![image-076.png](images/image-076.png)

If we print the addresses, we can clearly see that both(variable a, and lambda function variable a) variable have different addresses.

---

> ”[=]” using this as capture list it will grab all variable from the surrounding scope. (To capture value)

> ”[#]” using this as capture list it will grab all variable from the surrounding scope. (To capture as 	       	references)

> using reference, all have same addresses.

---

**Function Template:**

**Function Template by value: Function Template is a mechanism in c++ to set up a blueprint for functions, But compiler going generate the actual code when it sees the function called. Means to avoid code repetition.**

![image-077.png](images/image-077.png)

Here there are multiple function overload. They are doing the work. To minimise this type of multiple overload of same work. We can use Template.

![image-078.png](images/image-078.png)

  “ T ” is a place holder for the data type function is going to receive as argument. But all argument data type **have to be same****(there  is a room for not same data type)**. When compiler see, template function called. It going to look at the data type of arguments which are passing to function. Then compiler generate same function with that data type only when the function is called .

> can also pass string by argument.

Function templates are not c++ code. It just a function blueprint.

![image-079.png](images/image-079.png)

If data types are not same passing as argument, we can  explicitly set the type with<double>. This basically tells the compiler to generate double/int etc. template instance function for this calling. And implicitly convert other type to determined type. In below example ”a” variable int type and will convert to double.

> We can see this internal conversion of function template on **cppinsights.io.**

![image-080.png](images/image-080.png)

 

This will give no error. Cause we explicitly tell to generate a double type template instance function. Otherwise, different type will not accept. Will throw an error.

If we use sizeof() to see size of the “re” variable. We can see is it double, int etc.

---

**Template ****type parameter by references: **Recall references procedure, template procedure. All same concept.

![image-081.png](images/image-081.png)

![image-082.png](images/image-082.png)

 
 function overloaded. Cause calling

     maximum(a,b); // this is used for both template with value and with reference. That’s why get confused.

---

 **Template Specialization: **This is specially for “const char pointer” like: 

```cpp
	const char* x=”asdf”;
```

for const char pointer regular method will not work. There is a special template mechanism for it.

![image-083.png](images/image-083.png)

 This does not compare like others in template. See 18:50 Hr

Instead it use c++ template library function “strcmp” to compare. See on www.cppreference.com about strcmp.

In order to use template specialization we have to declare primary template like below…

![image-084.png](images/image-084.png)

![image-085.png](images/image-085.png)

In order to use template specialization we have to declare primary template like below…

 

![image-086.png](images/image-086.png)

  Whole code:

![image-087.png](images/image-087.png)

 

---

**C++ 20:**

**Concept: Concept is a mechanism to set up constrain or restriction on template parameter of  our function template. For example we can set that function to be called only integer and we call it something which isn’t ans integer, it will give a compiler error.**

![image-088.png](images/image-088.png)

 

If we set double instead of int, this will compiler error. Cause we set “integral” type to accept as argument in function template.

These concepts are introduced in c++20. So use “-std=c++20” during compiling.

![image-089.png](images/image-089.png)

 

Concepts are introduced in c++20. Before that we can use this(below) inside function template. And set a custom message if condition does not meet.

![image-090.png](images/image-090.png)

  

**Type Traits: Intro on C++11. A type trait is a small template “tool” that tells you something about a type, or transforms a type, at compile time. On above we are checking “T” is an integral or not by “is_integral<>”. Boolean value. Also Use this as requires. See below**

![image-091.png](images/image-091.png)

 

We can use type traits on **requires**.

![image-092.png](images/image-092.png)

 

Some Type Traits:

![image-093.png](images/image-093.png)

 

Some ways to declare concepts:

![image-094.png](images/image-094.png)

  

  

![image-095.png](images/image-095.png)

Syntax 3 is only allowed for, when we use “auto”.(Below)

![image-096.png](images/image-096.png)

![image-097.png](images/image-097.png)

Example for Type Trait:

A type trait is a template utility in the C++ standard library (in <type_traits>) that allows you to query information about a type or transform a type at compile time.

Think of type traits as little “questions” or “tools” about types:

1. Is this type an integer?

2. Is this type const-qualified?

3. What happens if I remove a pointer from this type?

4. Are these two types the same?

![image-098.png](images/image-098.png)

**Here the compiler removes the unused branch at compile time → no runtime cost.**

Here without “constrxpr” if is checked at run time. So both branch(if, else) must compile because compiler doesn’t know which condition will be true.

But with “constexpr”

* if constexpr means the compiler chooses the branch at compile time.

* The unused branch is discarded before code generation — it’s as if it never existed. Means for (“print(42)”) compiler will keep only  if part. And for (“print(3.14)”) compiler will keep else part.

![image-099.png](images/image-099.png)

 
> Think f(42)=print(42)

Generated machine code for print(42) contains **no trace** of the "not integral" branch.
Generated machine code for print(3.14) contains **no trace** of the "integral" branch.

The compiler erases the irrelevant branch at compile time.

**Constexpr- is a keyword in c++. That tells to evaluate the value in compile time.**

See this from **cppinsights.io**  comparing with and without “constexpr”

![image-100.png](images/image-100.png)

  

![image-101.png](images/image-101.png)

 
---

**Build own Concept/Custom concept:**

**Example 1:**

![image-102.png](images/image-102.png)

 

Line- 9,10: Custom concept. Here we are setting function parameter have to integral type.

Line-13: function checks whether our parameter satisfy the concept. If one parameter is float it will give compiler error.

For int value the type trait (is_integral_v) is return true and concept is satisfied. And function template is gonna execute.

For double, float value we can use “is_floating_point<T>”.

Diff way to use concepts:

![image-103.png](images/image-103.png)

   

![image-104.png](images/image-104.png)

![image-105.png](images/image-105.png)

 

![image-106.png](images/image-106.png)

**Example 2:**

![image-107.png](images/image-107.png)

 

Line-10,11: requires 2 parameter which are multipliable. This will not give multiply of “a” ans “b” If pass (char)  concepts will not satisfy. Error

**Example 3: If we want “a” will be int and “b” will be double. See below. Use diff type name.**

![image-108.png](images/image-108.png)

 

---

Deep dig into ‘Requires’ :

![image-109.png](images/image-109.png)

  
 you can only put valid expressions involving the types/objects. requires doesn’t test boolean conditions — it just checks “is this expression well-formed?” check given expression is vakid or not.

Inside requires { ... }, each line is an expression requirement.

It only checks whether the expression is valid (well-formed) — not whether its value is true or false.

![image-110.png](images/image-110.png)

  

![image-111.png](images/image-111.png)

Here “sizeof(T)<=4” is simple requirement. Only check syntax.

Although b is double. It should give compiler error cause concepts does not meet(double size 8byte). It gives ans. Cause:

sizeof(T) <= 4 is always a valid expression (it produces a true value).

The compiler says  “requirement satisfied” regardless of whether the condition is true or false.

It doesn’t enforce the size check.

![image-112.png](images/image-112.png)

  

This is correct way to set sizeof(). This will check conditions are true or false. And this will give error cause ‘b’ size is 8 byte. We set <=4.

Or we can use nested requirement(requires inside requires). See below(No error)

![image-113.png](images/image-113.png)

 

Example *: Using Logical operator...
 

![image-114.png](images/image-114.png)

Example **:

![image-115.png](images/image-115.png)

---

**Exit(): **“exit(1)” terminate the whole program. So if this is also used in used in a function, it stop the entire program.

![image-116.png](images/image-116.png)

  

![image-117.png](images/image-117.png)

![image-118.png](images/image-118.png)

 

 exit(0) → “Program ended successfully.”

exit(1) → “Program ended due to an error.” // abnormal termination of the program

---

> If we pass an array to a function it pass its reference through pointer. Not a copy.

---

**OOP**

**Class:** Class is a mechanism to build our own type to use them like we have been using built in type(int, double). Its like a blueprint to create object.

**Object: An object is a real instance(copy) of that class. Like a actual car built from blueprint.**

![image-119.png](images/image-119.png)

 

* Public means after “public” all parameter are accessible outside of the class.

* If public is not defined. Then in general all parameter are indicated to private. Means can’t  access outside of the class. (Members of class are private by default).

* Public, private, protected are called access specifier.

* if public is not defined on above example. All member will be private. Line 19,20, 21 can’t write. Compiler will give error.

* Private members can be accessible from inside class.

* Objects(ob1) are run time data.

* Member variable should be set to private.

![image-120.png](images/image-120.png)

  
**1. Constructor:**

![image-121.png](images/image-121.png)

 

Constructor are 2 type.

1. Default constructor.  //Method have no parameter line: 13

2. Parameterized constructor. //Have parameter Line: 17

![image-122.png](images/image-122.png)

 

* This is how private members can be accessible inside class.

* If an object is declare default constructor will be called. Line: 13

* if not defined(default constructor), compiler will automatically generate default empty constructor.

Or inside main

“mycls ob1(12,22);” parameterized constructor will be called. Line: 17. default will not be called.

* If compiler sees any constructor, its not gonna generate default constructor.

* We can declare default constructor 2 ways; on line:13 & 16

![image-123.png](images/image-123.png)

 

---

**2. Setter & Getter:**

Private members are not accessible from outside. Both are methods to modify or read member variable of a class.

---

ifndef:

![image-124.png](images/image-124.png)

Means this constant is define on any other file of the project and we are not sure, we can use this. It says, if below code is not defined, I am defining here, else skip. Otherwise, if same things defined in many places, show error.

---

**“::” Scope Resolution Operator: Used when a function of a class us defined on other file.**

![image-125.png](images/image-125.png)

 
Here “Cylinder” constructor is belong to Cylinder class. We can use any function instead constructor.

But we have to mention function prototype inside the class. Like: **Cylinder(double red_…..);**

---

**Manage class object by Pointer:**

![image-126.png](images/image-126.png)

Here “ - >” is a dereferencing operator. Works like **(*c2).findcir();**

**c2 pointer will be on stack memory but obj will be on heap.**

Direct creating object creates on stack and with using pointer object will create on heap. Remember to release memory.

![image-127.png](images/image-127.png)

 

dangling pointer is dangerous. Holds old memory. So after deleting set **c2=nullptr;**

---

**3. Destructors:**

![image-128.png](images/image-128.png)

 
Destructors are called by the compiler to destroy our objects.

![image-129.png](images/image-129.png)

 
**When Destructor Called?**

> When local stack objects goes out of scape then destructor is going to be called by compiler.

> When heap object is released with delete.

> Destructor has no parameter.

> Destructor does not called by compiler automatically for heap data. We have to release memory like line 32(below)

> The compiler calls destructor for objects with automatic storage duration when they leave scope.

If I have 3 objects(d1,d2,d3), destructor will call 3 times. But in reverse order. ‘d3’ destructor will call 1st and d1 destructor in last.

![image-130.png](images/image-130.png)

 

Explained Below:

* “d1” is a local object. It destroyed when main() exits its scope after line 39 and before the program returns from main(line 41);

* ”d1” lives in stack. When main ends, C++ compiler automatically calls destructor. Memory released for ‘d1’ object.

![image-131.png](images/image-131.png)

In line 23 **string_view**

![image-132.png](images/image-132.png)

 

![image-133.png](images/image-133.png)

 

Diff Bet string_view & string:

![image-134.png](images/image-134.png)

![image-135.png](images/image-135.png)

![image-136.png](images/image-136.png)

Pass an object by value: see 22:00:00 hr

---

**4. “this” Pointer:  ‘this’ is a special kind of pointer, maintain by c++ to manipulate the current object. This ‘this’ pointer contains the address of the current object.**

![image-137.png](images/image-137.png)

 
```cpp
//"this" will print current object address
```

![image-138.png](images/image-138.png)

  
Not exactly pointing to the current object member(above).

**Chained call using Pointer:**

![image-139.png](images/image-139.png)

 

**Chained call using Reference:**

![image-140.png](images/image-140.png)

 

Here ‘const’ is important to include.

What happen in line: 33

![image-141.png](images/image-141.png)

 

---

**5. Struct Vs Classes: Struct is another way to  define classes. Differences:**

  

![image-142.png](images/image-142.png)

![image-143.png](images/image-143.png)

So We can use struct when we have public members. But both are almost same. We can use anyone.

---

**6. Size of the class objects: Size of the class objects depends on the member of the class, not functions.**

![image-144.png](images/image-144.png)

  
Here, string size is 32 byte whether I put no character or put millions of character. It will remain same.  We are not getting memory which occupy by characters, but getting the fixed size of the string object itself in the memory. It includes internal pointers, metadata(like length, capacity) and other housekeeping data.

If I put millions of characters inside string, it will store in separate dynamically allocated memory in the heap. 

![image-145.png](images/image-145.png)

Above is in general. But for small string, there may be diff scenario: below

![image-146.png](images/image-146.png)

   

![image-147.png](images/image-147.png)

 
Object size:

![image-148.png](images/image-148.png)

 

Here object size should be 44 byte. But Actual size is 48. cause, Alignment rule

![image-149.png](images/image-149.png)

  

**The total object size must be a multiple of the ******largest alignment****** (here: 8 bytes)**

so there will 4 byte padding after 4 byte integer memory. See memory layout: below

![image-150.png](images/image-150.png)

  
Here **Offset** is the byte position of a member inside an object, measured from the object start.

For functions:

![image-151.png](images/image-151.png)

 

**Inheritance**

**1. Inheritance: Inheritance in C++ is a mechanism that allows a new class (derived class) to inherit properties and behaviours (methods) from an existing class (base class), promoting code reuse and creating a hierarchical relationship between classes.**

When a class inherits another class, it gets all the accessible members of the parent class, and the child class can also redefine (override) or add new functionality to them.

![image-152.png](images/image-152.png)

 
 Public, private, protected are access specifier.

![image-153.png](images/image-153.png)

 

in the above example, player class inherits all public members of human. But can’t access private. That’s why we only can print ‘age’ variable. Also passing string through player object(”motaher”, “emon”) constructor will be unused. We have to use public setter & getter.

***Protected member: Sometime we may want that members of base class has to be accessible from derived class but still be inaccessible from outside. In that case use those member as protected member. Below:

![image-154.png](images/image-154.png)

  
***Base class access specifier:

![image-155.png](images/image-155.png)

Here” Public” is base class access specifier. This is public inheritance. This can be private/protected.

This tell how accessible the base class members to derived class.

![image-156.png](images/image-156.png)

  
Public Inheritance:

1. Anything public in base class, will remain public in derived class.

2. Anything protected in base class, will remain protected in derived class.

3. Private members are never inherited. Derived class can’t access.

Others(private, protected) we can derived from our assumption.

![image-157.png](images/image-157.png)

  

![image-158.png](images/image-158.png)

  

![image-159.png](images/image-159.png)

 

![image-160.png](images/image-160.png)

 
Here, Engineer class is inherited by CivilEngr class. And Person class is inherited by  Engineer class privately. So CivilEngr class can’t access any member from person class. Cause all members(except m_3) from base class(person) is private to Engineer class. Engineer class can access. But can’t CivilEngr..

But But But

C++ allow us do something else so we can access from civilEng class.

we can use m_1, m_2 member in CivilClass by using “using” keyword. See below:

![image-161.png](images/image-161.png)

  

![image-162.png](images/image-162.png)

  

![image-163.png](images/image-163.png)

 
Here ‘using’ does is Bring member ‘pMotherName’ from class A into current class scope. It re-expose the member.

Though “pMotherName” member is protected. We can use in myFamily class, explained below:

![image-164.png](images/image-164.png)

 

---

**2. Default Arc Constructor with inheritance:**

Always provide default constructor for classes. Because compiler may calls these default constructor, specially if the class of inheritance.

![image-165.png](images/image-165.png)

  
If we build a civilengr object and we don’t have a default constructor for person class, compiler is going to call that, but will not find and give error.

Compiler will go for base class first then the other layer which was inherited to call all the constructor.

---

**3. ****Initializer List:**

Give a variable/object its **first valid value at the moment it is created**.

![image-166.png](images/image-166.png)

                                                                                                               

 

![image-167.png](images/image-167.png)

![image-168.png](images/image-168.png)

![image-169.png](images/image-169.png)

![image-170.png](images/image-170.png)

   

**Explain:** Initializer List vs Assignment

![image-171.png](images/image-171.png)

  

![image-172.png](images/image-172.png)

 
---

**4. ****Custom constructor with Inheritance:**

Some time we need to call custom constructor to be called instead of default with many parameter.

![image-173.png](images/image-173.png)

  
The car class constructor uses an **initializer list** to initialize both the base class and its own members.

**Initializer List:** :vehicle(vname, weight, brName), doorNumber(drnumber)

- ** :vehicle(...)** - Calls the base class vehicle constructor, passing the name, weight, and brand name to initialize inherited members

- ** doorNumber(drnumber)** - Initializes the doorNumber member variable with the provided value

![image-174.png](images/image-174.png)

---

**5. ****Copy Constructors with Inheritance: **A **copy constructor** in C++ is a member function that **initializes a new object using an existing object of the same class**. It is the standard mechanism for duplicating object data and takes a reference to the source object as its parameter.

 

![image-175.png](images/image-175.png)

Here  a new object initialize using existing object(manus).

![image-176.png](images/image-176.png)

 
Here, in Line 20: copy constructor of human class is receiving an object reference and initialize the member value from the source.

~~~

	human(source);//line 34

~~~

this means: copy the human portion from the source using human copy constructor(line 34)

~~~

	human(const human& source); //line 20 or 34 same

~~~

This Means: Take a human object by reference.

**Flow chart for above code:**

→ player “manus” object is created.

→ player copy constructor called for “manus1” and passing “manus” object as  as constant reference

→ human(source) executed

→ human copy constructor received a object reference of “manus” and copy its part and initialize “manus1” members of human class.

→ Back to the player copy constructor. And copy and initialize player class member for “manus1”.

![image-177.png](images/image-177.png)

 

When do we need:

![image-178.png](images/image-178.png)

 

![image-179.png](images/image-179.png)

 

![image-180.png](images/image-180.png)

 

## Core rule (very important)

“Copy constructor is NOT for normal use — it is for **creating a new independent object with same state when the program explicitly needs duplication.”**

---

**6. Inheriting Base Constructor:          // introduced in C++11**

Base constructors are not inherited by default. Means it is not possible to use  base constructor by derived class. But it is possible to tell compiler to use the base constructor to set up our own objects. How? See below:

![image-181.png](images/image-181.png)

 

line 26 says: when building player object,, don’t use your own constructors instead set up a base like constructor which is going to only initialize the base member variable. And compiler is going to generate a constructor that may looks like below:

![image-182.png](images/image-182.png)

 
**using human::human;** makes all accessible constructors of the base class (human) available in the derived class (player). The compiler generates forwarding constructors that call the corresponding base-class constructors.

***A derived class can still define its own constructors even when using using Base::Base;. Both inherited constructors and user-defined constructors may coexist.

> Only accessible constructors are inherited. Private constructors of the base class cannot be inherited.

Constructor name will be derived class name. This is going to forwarding the work to initialize our object throw the player class. This is called Inheriting base constructor.

Generally it is not recommended to use unless we don’t have other option.

Q: if i have default constructor and parameterized constructor, which one will inherit if use "using human::human;"

Ans: **using Human::Human;** inherits **all accessible constructors** from the base class, not just one.

![image-183.png](images/image-183.png)

 

**using Base::Base;** inherits **every accessible constructor** from the base class (default, parameterized, copy, move, etc., if applicable). If the derived class declares a constructor with the same signature, the derived-class constructor takes precedence for that signature.

---

**7. Inheritance with Destructor:  **As we know, When creating a derived-class object, constructors are called **from base to derived**. **But** Destructor are called in reverse order. From above example, player class destructor(derived class) will call 1st, then human(base) class destructor will class. If we have 3 layer of inheritance as videos, CivilEnginne destructor called 1st, then Engineer, then Person class destructor.

In C++, destructors in inheritance are mainly about **order of destruction.**

![image-184.png](images/image-184.png)

 
See above: Destructor’s are called in reverse order.

---

**8. Reused symbols in Inheritance: We can use same names of parameter/methods in inheritance hierarchy. Means Base class and derived class can have same name of parameter/methods.**

If we have same method on child and parent class and call the method, what C++ does is, it is going to override/hide the parent class method/parameter and use the child class method/parameter

![image-185.png](images/image-185.png)

     
­--------------------------------

**Polymorphism**

Polymorphism is an OOP concepts that allows a same function or operator to behave differently in different scenarios depending on the objects that uses it. Polymorphism means "many forms".

```cpp
For Example;
```

The “+”   operator in C++ is used to perform two specific functions. When it is used with numbers, it performs addition. And when we use the + operator with strings, it performs string concatenation.

**Key Idea is:** one interface- many implementation..

Types:

- Compile Time(Static) Polymorphism: The compiler decides which function/operator to call.

- Runtime time(Dynamic) polymorphism: The function call(which will be called)is decided while the program is running based on the object being used.

![image-186.png](images/image-186.png)

 
**Compile Time(Static) Polymorphism: Compile-time polymorphism is also known as static polymorphism or early binding. In this type of polymorphism, the compiler decides which function or operator to call during compilation.**

**1. Function Overloading: In C++, we can use two functions having the same name if they have different parameters (either types or number of arguments).  And, depending upon the number/type of arguments, different functions are called. For example,  See the link(Click): Example**

In case of OOP example:

![image-187.png](images/image-187.png)

 
The class Geeks contains two overloaded functions named add(), one for integers and one for double values.

When add(10, 2) is called, the integer version is executed; when add(5.3, 6.2) is called, the double version is executed. The compiler decides which function to call at compile time based on the argument types, demonstrating function overloading.

---

**2. Operator Overloading: **In C++, we can define how operators behave for user-defined types like class and structures. For example,

The + operator, when used with values of type int, returns their sum. However, when used with objects of a user-defined type, it is an error.

In this case, we can define the behaviour of the + operator to work with objects as well.

This concept of defining operators to work with objects and structure variables is known as **operator overloading**.

***************Note: ****Most operators in C++ can be overloaded, but operators such as “::”,  “ . ”,  “.*”,   “?:” and sizeof cannot be overloaded because they are essential to the core functionality of the language.

**Syntax:**

![image-188.png](images/image-188.png)

 

Example to add 2 complex number:

Version I:

![image-189.png](images/image-189.png)

   
(Above code)Normally, + only works on built-in types like int or float. When you write 1 + 2, the compiler knows how to add raw numbers. But c1 + c2 where c1 and c2 are Complex objects means nothing to the compiler by default — it doesn't know what "adding" two objects should mean.

Operator overloading lets you **teach the compiler what ****+**** should do** when it sees two Complex objects on either side of it. Under the hood, c1 + c2 literally gets translated by the compiler into a function call. Overloading just means: "when you see this operator with these operand types, call this function instead of giving an error."

The compiler rewrites line 20(Complex c3 = c1 + c2;) internally as:

![image-190.png](images/image-190.png)

 

So:

- c1 is the object the method is called **on** — that's why inside the function, real and imag (no prefix) refer to c1's members.

- c2 is the **argument** passed in — that's obj inside the function.

- The function returns a brand-new Complex built from the sums, and that becomes c3.

“operator+” is just a member function(of the class) (a weird-looking one) that takes one parameter, because the left-hand object is implicitly “this”.

Version II:

![image-191.png](images/image-191.png)

 
Here, operator+ is **not** a member of the class — it's declared friend, meaning it's a regular standalone function that's just been granted permission to access the class's private members (real, img).

The compiler rewrites line 20(Complex c3 = c1 + c2;) internally as:

19

![image-192.png](images/image-192.png)

 

Notice the difference: now **both** operands are explicit parameters, **obj1** and **obj2**. There's no implicit **“****this”****,** because this function isn't attached to any particular object — it's a free function that happens to live inside the class definition (for organizational convenience) and gets **friend** access to read private data.

Q: Tell me what is **Friend function**?

Ans: A **friend function** is a function that is **not a member** of a class, but is still given **special permission to access the class's private and protected members**, as if it were a member.

Sometimes we may need to access private members of a class from outside. Friend function gives us that scope.

write the function signature inside the class, with the “**friend”** keyword in front. That's just a declaration — it tells the compiler "this function, even though it's defined elsewhere (or right here), gets access to my private stuff."

![image-193.png](images/image-193.png)

 
---

**Runtime(Dynamic) Polymorphism: Runtime polymorphism is also known as dynamic polymorphism or late binding. In this type, the function call is resolved during program execution instead of compilation.**
 

![image-194.png](images/image-194.png)

---

**3. Function Overriding: **Function Overriding occurs when a derived class defines one or more member functions of the base class. That base function is said to be overridden. The base class function must be declared as **virtual function** for runtime polymorphism to happen.

Suppose we define the same function in both the base class and the derived class. Now, when we call this function using the object of the derived class, the function of the derived class executes.

Here, the member function in the derived class shadows the member function in the base class. This is called shadowing the base class member function.

![image-195.png](images/image-195.png)

 
Here, the print() from Derived is executed by shadowing the function in Base.

To access the shadowed function of the base class, we use the scope resolution operator :: . (below line 24)

We can also access the shadowed function by using a pointer of the base class to point to an object of the derived class and then calling the function from that pointer.

![image-196.png](images/image-196.png)

 

Call the Shadowed function from derived class(below)

![image-197.png](images/image-197.png)

 

Notice the code Base::print();, which calls the member function print() from the Base class inside the Derived class.(above)

Using Pointer:

(without virtual function)

> N.B: This is not example of polymorphism. Example of Static binding

![image-198.png](images/image-198.png)

Img-1

Here(above), Base type pointer points to the Derived object “derived1”. When we call the print() function using ptr, it calls the member function from Base. Without virtual, C++ uses **static binding** (also called compile-time binding). The compiler looks at the **type of the pointer** (Base*) and decides at compile time: "this pointer is Base*, so call Base::print()." It doesn't matter what object the pointer actually points to at runtime — the pointer's declared type wins.

In order to override the Base function instead of accessing it, we need to use **virtual functions** in the Base class(see below example).

(with virtual function)

> N.B: This is the example of polymorphism(runtime)

![image-199.png](images/image-199.png)

Img-2

With virtual, C++ uses **dynamic binding** (runtime binding). The compiler inserts a lookup through a **vtable** (virtual table) — a hidden table of function pointers attached to the object — so the decision of which function to call is deferred to runtime, based on the **actual type of the object**, not the pointer type.

override doesn't change runtime behaviour at all — it's a **compile-time safety check**. It tells the compiler "I intend for this function to override a virtual function from the base class." If you make a typo in the signature (wrong parameters, wrong const-ness, etc.), the compiler will throw an error instead of silently creating a new, unrelated function.

![image-200.png](images/image-200.png)

 

Without virtual, C++ chooses the function based on the **type of the pointer/reference** (compile time).

With virtual, C++ chooses the function based on the **actual type of the object** (runtime).

So, **virtual**** enables runtime polymorphism**, while **override**** is a safety feature** that helps ensure your derived function really overrides the intended virtual function.

![image-201.png](images/image-201.png)

 
**Virtual Functions and Function Overriding: **A virtual function is a member function in the base class that we expect to redefine in derived classes. The print() method in the Derived class shadows the print()  method in the Base class. However, if we create a pointer of Base type to point to an object of Derived class and call the print() function, it calls the print() function of the Base class.

To avoid this, we declare the print() function of the Base class as virtual by using the virtual keyword.

If the virtual function is redefined in the derived class, the function in the derived class is executed even if it is called using a pointer of the base class object pointing to a derived class object. In such a case, the function is said to be overridden.

---

**Size of Polymorphic object: Below  image with polymorphism(dynamic binding)**

![image-202.png](images/image-202.png)

  
Below image without polymorphism(only removed “virtual” keyword)

 

![image-203.png](images/image-203.png)

Above 2 image we can see, Size are different.

**A**** polymorphic object is usually larger than a non-polymorphic object**. The reason is that the compiler adds a **hidden pointer** called the ****vptr****** (virtual pointer)**. A class becomes polymorphic if it has **at least one virtual function**.

Each object of a polymorphic class contains a hidden pointer:

![image-204.png](images/image-204.png)

 

The vptr points to a **virtual table (vtable)**, which stores the addresses of the class's virtual functions. Without the vptr, the program would have no way to determine which virtual function should be called at runtime.

**In short, compiler need to track the information that allows to dynamically resolve virtual function calls.**

![image-205.png](images/image-205.png)

 

### Is there one vptr or one vtable?

- **Each object has its own ****vptr****.**

- **Each class has one ****vtable** (in the common case).

---

**Slicing:**

![image-206.png](images/image-206.png)

 

In the above image, “Shape” is base class. Oval class is inheriting Shape class publicly, Circle class is inheriting Oval class publicly.

![image-207.png](images/image-207.png)

 

In above image(line: 4), we are assigning a circle object to a shape object.(here not using pointer/reference)

Here compiler will notice that circle object has a part of shape class. So it will slicing off the extra part of Circle object except shape class part. And then assign shape object variable and that we are going to get in memory. This because, compiler will see this variable(shape2) has no enough memory to store all data of the circle object. Explained in the below image,

![image-208.png](images/image-208.png)

 

![image-209.png](images/image-209.png)

 
In the above example derived object takes 2 parameters(a and b). But due to slicing, we only get Base class part, where i=45.

---

**Polymorphic Object Stored in collections:**

![image-210.png](images/image-210.png)

 

Here(above) Storing the derived object in Shape class type array. So extra part of the objects will be slice off. In the array, only Shape part of the objects will be stored in the array. Also here copies of the object is stored, not reference.

![image-211.png](images/image-211.png)

 
“shapes2[]” is shape type array of reference. C++ **does not allow arrays of references**. Because reference is just another name of a variable. And array is designed to modify data which is stored. But reference can’t be modified or changes.

But Store in pointers works also no slicing off. Means all will be stored. (below)

![image-212.png](images/image-212.png)

 
Draw(); method will be called in polymorphic way.

Also works for Smart Pointer as below

![image-213.png](images/image-213.png)

 

---

**Inheritance & Polymorphism with Static Variable: See 1st Static Variable**

**Static class Member: **A static data member is shared by **all objects** of the class — there's only one copy, not one per object.

![image-214.png](images/image-214.png)

  

Another Example:
 

![image-215.png](images/image-215.png)

Here(above) Ellipse is a Shape. So total object is 6. But in below code… We can also track only ellipse object count by same variable(obj_count).
 

![image-216.png](images/image-216.png)

We can see obj count(obj_count) variables are same in both class. Now Ellipse object count variable is going to maintain its own static variable and Shape also.

**Shape::obj_count**** and ****Ellipse::obj_count**** are two completely different static variables.** They just happen to have the same name. These are two different variables stored at different memory locations.

**4. Static Member Function: **Can be called without creating an object, and can only access static members (no access to this or non-static members).

![image-217.png](images/image-217.png)

 

---

**“Final” in Inheritance: “Final” Key allow us to Restrict**

1. Final virtual function/ function (override method in derived class)

2. Final Class(base class)

**1. Final virtual function/ function:**

![image-218.png](images/image-218.png)

 

```cpp
Shape::draw() method is final. Means no downstream class(derived class: Circle) can override this method. This is used to restrict, how we can override our own virtual methods in downstream classes(derived class).
```

**2.  ****Final Class: **A class marked final **cannot be inherited**.
 

![image-219.png](images/image-219.png)

Above, Director is final. So Director class can’t be inherited.

---

**Virtual functions with  Default Argument:**

![image-220.png](images/image-220.png)

 

Here a=5, b=5 are default argument. Things to remember(below)

![image-221.png](images/image-221.png)

 
See Videos for details: 29:09:17 hour https://www.youtube.com/watch?v=8jLOx1hD3_o

It is recommended not to use default arguments.

---

**Virtual Destructor:  Remember previous example. Ellipse class inherit Shape class publicly. So if we create a Ellipse class object and when its times to destroy object, the order of the destructor call  is: 1st Ellipse class destructor called then Shape class destructor called.**

![image-222.png](images/image-222.png)

 
Problem is arise when we use base pointer to manage derived class objects. How?

![image-223.png](images/image-223.png)

 
So derived class object destructor not called.!! Because our destructor is not virtual. The compiler is going to use static binding  by seeing Shape type of the pointer, and decide at compile time which destructor to called.

So after using virtual destructor, this will show polymorphic behaviour, and call the actual type of the object destructor. And release the memory. As below

![image-224.png](images/image-224.png)

 
Remember, without virtual destructor, any kind of dynamic memory(not the shape part) we might have allocated in the constructor for Ellipse is going to leaked out. Here, meaning Ellipse part which will use in dynamic memory allocation. Suppose a variable of Ellipse class part(not inherited part).

See Link(virtual destructor) for more… https://www.programiz.com/cpp-programming/virtual-functions

---

**Dynamic Cast: **dynamic_cast is a C++ casting operator used to **safely convert pointers or references within an inheritance hierarchy at runtime**.

In some cases we need to call/access non-polymorphic methods of the derived class and we have a pointer o base class pointing to the derived class objects. Then the pointer have no idea about non-polymorphic methods.
 

![image-225.png](images/image-225.png)

On the above example, see :line 29. Error.

Below we can access such methods by using Dynamic_cast

![image-226.png](images/image-226.png)

 

dynamic_cast safely converts a base class pointer to a derived class pointer at runtime. If the conversion is valid, it returns the converted pointer; otherwise, it returns nullptr.

“ptr” is a base class pointer pointing to a Derived1 object. dynamic_cast checks the actual object type at runtime. Since the object is of type Derived1, the cast succeeds. A valid Derived* pointer is returned.

For downcasting to work, the base class must be polymorphic. A class becomes polymorphic when it contains at least one virtual function.

If the base class doesn’t contain any virtual function then, it is not polymorphic.As a result, dynamic_cast cannot perform runtime type checking and compilation fails.

> Requires the base class to have at least one virtual function to apply Dynamic_cast

![image-227.png](images/image-227.png)

 

It is required to check whether, dynamic_cast successful or not. Like below:

![image-228.png](images/image-228.png)

  

When Casting will failed:

![image-229.png](images/image-229.png)

 
bp points to a Derived1 object. The code attempts to convert it to Derived2*. Since the object is not of type Derived2, the conversion is invalid. dynamic_cast returns nullptr.

Like pointer we can use references. As below:

![image-230.png](images/image-230.png)

 
When Casting fails?

dynamic_cast can fail when the **actual object at runtime is not compatible with the type you're trying to cast to**.

![image-231.png](images/image-231.png)

 

Here, pointer type is animal, object type is cat. We want to cast to dog. But Dog is not a cat, means Dog is not derived class of cat. So casting fails.

In terms of reference, references cannot be nullptr. Instead, dynamic_cast throws: “std::bad_cast”

In case of checking casting fails or not  we use if,else for pointer. But for reference we can use try catch since it throws an exception, like below:

![image-232.png](images/image-232.png)

 

---

While polymorphism works, see how constructor and destructor called. Below:

![image-233.png](images/image-233.png)

 

1. Base Constructor Called

2. Derived Constructor Called

3. Derived Destructor Called

4. Base Destructor Called

***Never call virtual(Polymorphic) function from constructor and destruction. To know details See: 30:08:23 Hour.(on the video)

![image-234.png](images/image-234.png)

 
---

**Pure Virtual function & Abstract Class:**

**Pure Vir****tual function: **A **pure virtual function** is a virtual function that the base class declares but does not provide a required implementation. It forces any child class to write its own version of this function.

![image-235.png](images/image-235.png)

 

The  “= 0” is what makes it **pure virtual**.

It basically says, “Every derived class must provide its own draw().”

![image-236.png](images/image-236.png)

 

Here, Circle provides an implementation for draw().

**Abstract Class: **A class containing **at least one pure virtual function** is called an **abstract class**.

**cannot create an object** of an abstract class. But we can create a pointer/reference:

***Derived class must provide the definition of pure virtual class. If a derived class doesn’t provide it, then this derived class have to be Abstract class. Also can’t create object of that derived class since this is also a abstract class.

**We ****can provide a definition** for a pure virtual function outside the class:

![image-237.png](images/image-237.png)

 

***Pure virtual means the function makes the class abstract; it does not necessarily mean the function can never have a definition.

Abstract class can the normal methods. And we call call them. Below: (Line 18)

![image-238.png](images/image-238.png)

 

Also This way: below

![image-239.png](images/image-239.png)

 
> Abstract class can have both constructor and destructor.

Why need abstract class and pure virtual function?

![image-240.png](images/image-240.png)

 
Here(above), shape is a base class, and Circle, Rectangle is derived-class. Shape is abstract class by not defining the Perimeter and surface function. Derived must define the function.

Since shape class doesn’t know which parameter need to define the perimeter and surface function. It let the derived to define cause the parameters needs to calculate the perimeter of Circle are diff then the perimeter of Rectangle. This is how abstract class and pure virtual function become useful.

Also a shape can be a Rectangle, Circle, Triangle etc. So let the derived-class to define what it needed.

---

**Interface: An interface is a specification of something that will be fully implemented in a derived class but the specification itself resides in the abstract class.**

An abstract class with only pure virtual functions and no member variable can be used as interfaces.

***Class can inherit many interfaces. 


---

<div align="center">

*📚 Notes by [ChemistCoder90](https://github.com/ChemistCoder90) — MSc Chemistry, SUST*

</div>
