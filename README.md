# C++ Notes
> Based on: *"C++: 31 hours long video of FreeCodeCamp"*  
> Author: **Emon_SUST** | 01714076452

---

“C++: 31 hours long video of freecodecamp”

“Emon_SUST 01714076452”


## Features:

supports data abstruction, means Data abstraction is a fundamental concept in computer science and tsoftware engineering that involves hiding the implementation details of data types and exposing only the essential features or behaviour to the outside world. Data abstraction is a powerful concept that facilitates the design, implementation, and maintenance of complex software systems by providing clear interfaces, encapsulating implementation details, promoting modularity, and supporting information hiding.

---


Statement: A statement is a basic unit of computation in a C++ program. Ends with a semicolon(;).
They are executed from top to bottom when program is run.

---


![img001](images/img001.png)
-----------------------------------------

![img002](images/img002.png)
input For Space separated word


Variable: A piece of memory that used to store specific type of data.

Number System representation:

![img003](images/img003.png)

*** Modifier like signed, unsigned used integral data type as decimal number/ whole number. Can’t use for float, double(2.0, 2.5).


## Float and Double:


![img004](images/img004.png)

**Precision includes digits before decimal point(.). 12547.325-> 12547 included in the precision.
For Float: 12345.6789-> 89will be garbage value. Cause precision 7 for Float. May print like: 12345.6725
** float a=123456789-> 89 will b garbage value. May print like: 12345.6745


![img005](images/img005.png)

Floatiing point number memory representation is not similar to deciaml number. It explained in IEEE_754 -> IEEE_754-> Press ctrl & Click


![img006](images/img006.png)


![img007](images/img007.png)

cout<<setprecision(20);

![img008](images/img008.png)


If we not set precision, the default precision will be 6 digits.(Total digits. Not after decimal point)
if we use “fixed” the with set precision(4), precision will be 4 after decimal point. Above a=12.1234;(ans)
But not using “fixed” precision will be 4 for total digits. Above a=12.12;(ans)
used for set precision. Library> #include<iomanip>

suffixes(like f, L): u // unsigned
ul // unsigned long
ll // long long

---


**Booleans occupy 1byte/8bits in memory.
bool x=true; // or bool x=1;
bool y=false; // or bool y=0;
cout<<boolalpha; //used for printf true/false instead of 0/1
cout<<x<<” ”<<y;
will print true, false.

---


## Character:


![img009](images/img009.png)

![img010](images/img010.png)
------------------------------

![img011](images/img011.png)

** 31/10 means how many times 10 is gonna fit in 31. so ans is 3.
* Relation Operator: > ,< , >=, <=
* Logical Operator: &&, ||, !

---

Manipulator: https://en.cppreference.com/w/cpp/io/manip //for more

* std:flush: when we print something, it does not go directly to the terminal. It store somewhere called “buffer”. When buffer is full/ complete it goes to terminal. If use std:flush data directly goes to console/terminal instead of goes to buffer.

![img012](images/img012.png)


*setw() : set width
cout<<right; // printf from right. 
Left for left alinement

![img013](images/img013.png)


cout<<setfill(‘-’) // blank space fill with ‘-’

![img014](images/img014.png)


*for finding max min numeric number limits data type can hold.
Need this> #include<limits>

![img015](images/img015.png)
https://en.cppreference.com/w/cpp/types/numeric_limits


---

#include<cmath> : abs(), pow(), ceil(), log(), sqrt(), sin(), tan() etc https://en.cppreference.com/w/cpp/header/cmath
for log(): log(10) means loge(10). So have to fix the base as log10(10). E=2.71..
* round(): 3.5 will make 4, and 3.49 will make 3.

---


![img016](images/img016.png)

if we take data type less than 4 byte and perform arithmatic operation compiler automatically convert it to 4 byte. This behavior also present on other operator like bitwise operator.(>>, <<)

---

flow control: if else, switch, ternary operator.
*Switch: if we not use “Break”, the case which match, after that all case will execute and print every case value.
* we can use int, char , double, enum etc but not string as case.

---

* If we use “const” before array. We cant modify array elements.
* a[ ]={2,3,7,5,2,3}; size(a) return the size of array. /Or sizeof(a)/sizeof(a[0]);


Enum: An enum is a special type that represents a group of constants (unchangeable values).
To create an enum, use the enum keyword, followed by the name of the enum, and separate the enum items with a comma.

![img017](images/img017.png)


Enum is short for "enumerations", which means "specifically listed".
To access the enum, you must create a variable of it.
Inside the main() method, specify the enum keyword, followed by the name of the enum (Level) and then the name of the enum variable (myVar in this example):

![img018](images/img018.png)

By default, the first item (LOW) has the value 0, the second (MEDIUM) has the value 1, etc.
If you now try to print myVar, it will output 1, which represents MEDIUM:

![img019](images/img019.png)


As you know, the first item of an enum has the value 0. The second has the value 1, and so on. To make more sense of the values, you can easily change them:

![img020](images/img020.png)


Note that if you assign a value to one specific item, the next items will update their numbers accordingly:


![img021](images/img021.png)


Example:

![img022](images/img022.png)


## Why And When To Use Enums?

Enums are used to give names to constants, which makes the code easier to read and maintain. Use enums when you have values that you know aren't going to change, like month days, days, colours, deck of cards, etc.


## Pointer


Pointer is special kind of variable.
int* int_num{}; or int* int_num; // will point to a integer type variable //initialise with null 


 // pointer(nulptr)
double* frac_num{}; // will point to a double type variable
int * int_num{}; // this initialisation with {} is going to initialise with special address means it is not 


//pointing any variable. Means initialize with nullptr
int * int_num{nullptr}; // this pointer not pointer anywhere
** pointer of int, double, char etc all are same size. Cause they only store address.

Char *ptr{“Hello world”}; // Pointer will point to 1st character. Some compiler will not compile(MSVC). GCC will give warning and compile. A whole string is assigning to char type pointer. See:10:17:00
Cout<<ptr; // will print whole string.
Cout<<*ptr;// print 1st character ‘H’;
*ptr=’B’;// this may give error. Cause compiler will think it as const char array.
If want to modify. Don’t use character pointer, use array like: char msg[10]==”Hello world”;
or use const char *ptr{“Hello world”}; // no warning. Can’t modify also.

Dereferencing pointer: reading something(value) on the address of the pointer. Cout<<*ptr;
string with pointer: char* p_msg= “Hello World!”; // the pointer will point to the 1st character of string
*this will compile with warning. Use const char* p_msg= “Hello World!”;
printf p_msg will print whole string. But using dereferencing will print 1st character(*p_msg).
*** without const it gives warning/refuse to compile cause compiler is going to convert string into char array of constant char. What we are using is points to that is not a const char pointer. So pointer here might be used to try or modify data. That’s why it refuse unless using const.
Check at 10:17min

int *ptr;// contain junk address
int a=12;
*ptr=&a;
uninitialized pointer contain junk address. Assigning a value to it(*ptr=12)May cause error. Could be point to a memory which is used by OS. May cause disaster.
Use this: int a; int *ptr=&a;


![img023](images/img023.png)


## Memory Map

When we run a program it runs on RAM. Various program of OS or other is running on memory.

![img024](images/img024.png)


![img025](images/img025.png)

This process thinks it own 0~2N amount of memory which is virtual memory.
When we run a program it is going to go through a CPU section called memory management unit(MMU).

![img026](images/img026.png)
Part that are likely not to be used are discarded from the RAM.
MMU really does is, helps us mapping between the memory map in ur program and the real thing we have in RAM.
If we run few program, they are going to go through MMU and MMU is going assign them real section on RAM


![img027](images/img027.png)

* Since program thinks it 2n -1 memory, The MMU is going to transform between the idea the program has and the RAM we have(assigned memory by MMU).
* The memory map/Structure of program is standard format defined by OS. That’s why we can’t run directly window program on Linux.
*Memory map is divided into a lot parts


![img028](images/img028.png)

* STACK: Local variable stores on stack section.
* print, statement, function calls others store on stack section.
* TEXT:Actual binary load on Text so that CPU can execute it.
* HEAP:Additional memory when we run out of stack memory also to make things better for program, Used for run time.


## Dynamic Memory Allocation


![img029](images/img029.png)

2nd point- full Control: when declare a variable a=23; in stack it remove when scope is over. Developer doesn’t have full control. But in heap developer have full control when a variable comes to work and dies.
>> 10:41 min

![img030](images/img030.png)

*set up a pointer which point to heap memory.
After initializing a pointer with nullptr. When p_number4=new int execute the OS is allocate a memory on heap. Variables are usually stores on stack section. It removes when variable containing scope will over. But if we allocate a memory on heap by “p_number4=new int;” . This memory will live though its scope is over. It will stay until return it to operating system. To return:

![img031](images/img031.png)


Use ‘delete’ to return memory to the operating system. After return reset pointer to ‘nullptr’ is good to make it clear that no valid data pointer is pointing.
* Using ‘delete’ remove the allocated heap memory which is pointed. Not the pointer. If pointing to ‘nullptr’, delete will do nothing.
*** Always remember to release memory.

*Dangling Pointer: A pointer that doesn’t point to a valid memory address. Trying to dereferencing and using a dangling pointer will results in undefined behaviour.

How dangling pointer create:
1. Uninitialized pointer.
2. Delete pointer
3. Multiple pointer points to same memory.

Solution:
1. Initialize pointer. Either with valid address or nullptr.
2. Reset pointer after delete.(Either with valid address or nullptr.)
3. For multiple pointer point to same address, make sure master pointer is clear/ reset.
*** Always check if pointer is nullptr or not by if-else.


‘New’ fails:
When allocating an array with pointer with huge size(1000000000000000000). It may fails and program can crash. We can use exception mechanism or ‘nothrow’ to prevent crashing.

![img032](images/img032.png)


Both allocation (with for loop or without) fail.
* Solve with ‘exception mechanism’:

![img033](images/img033.png)


With ‘exception’ we can catch the problem. What is called ‘handle’ in the problem. Suppose we are going to set up color and color fails. UI(interface) may show black and white. But program will keep running “what()” function will show the error.
*with ‘nothrow’: If “new” fails, we are going to get “nullptr” stored.

![img034](images/img034.png)


For clear understanding see
https://www.youtube.com/watch?v=uoCuMTzD9AE&list=PLgH5QX0i9K3q0ZKeXtF--CZ0PdH1sSbYL&index=90 // anisul islam lecture 92. Exception handling


## NULL pointer safety:


![img035](images/img035.png)


check if null or not.

![img036](images/img036.png)
Or,

![img037](images/img037.png)
Pointer address implicitly converted into boolean. (null==0).
* After use delete set pointer to nullptr for safety.

---


Memory Leaks:

![img038](images/img038.png)


![img039](images/img039.png)
while 2nd allocation, pointer changes its pointing location to 2nd memory. Don’t have access of 1st memory(55).
Should delete 1st then allocate 2nd.

![img040](images/img040.png)


After local scope is over, pointer is gonna die, but allocated memory will remain and loose access.
These memory leaks may causes program crash.

Dynamic array: Array stores on the heap.

![img041](images/img041.png)


![img042](images/img042.png)

Release Memory:

![img043](images/img043.png)


Dynamic arrays are created at run time not compile time.
Explanation
![img044](images/img044.png)
:

![img045](images/img045.png)


![img046](images/img046.png)


Reference: A reference is an alias (another name) for an existing variable. It does not create a new variable or occupy memory, it just gives another way to access the same memory.

![img047](images/img047.png)


If we change reference value or variable value, both contribute same changes.
** “&ref” and “&s” both has same memory address.

![img048](images/img048.png)


![img049](images/img049.png)
Reassign a Pointer to others variable, but reference can’t.

![img050](images/img050.png)


Here ‘S and ref’ value will changes to 12.
Use case: *if want to modify original variable inside a function. This save memories.

![img051](images/img051.png)


* Return reference by function to a local or global variable.


![img052](images/img052.png)


![img053](images/img053.png)

* Using “const” before reference makes the variable unchangeable. This constant only applies to reference. Not variable. Can’t changes variable value with “const reference”. But variable itself can changes its value.

![img054](images/img054.png)


Value will changes to 12.

---


*** size(), sizeof() function return the size. But for character array it includes ‘null’ . But for string size() don’t count null.
*** strlen() is used for character array. Not for string.
char *a=”asdf”; // this is string literal. Not modifiable.
Char a[]=”asdf”; // this is character array. Modifiable. Use stack memory.
Using “const” is safe in string literal.
***String literal is actually a character array. When we assign it to “const char * ”, it automatically converts into a pointer to 1st element.
Const char *msg=”Hello I am here.”;

![img055](images/img055.png)

Character array lives on read only memory. Can’t modify.

---

swap 2 number.
1. a=a+b; b=a-b; a=a-b;
2. a=a^b; b=a^b; a=a^b;

---


Returning from function as Reference: Usually function returns values(int, char etc). But sometime compilers are smart enough that that return reference instead of values. Avoid copies. See below

![img056](images/img056.png)
Example:

![img057](images/img057.png)

![img058](images/img058.png)


Output:


Here both addresses are same. Its returns the reference. Using reference mechanism.

---

Function Overloaded: Means we can declare multiple function with same name in the same scope, but with different parameter lists. Like parameter type(int, double, float).


![img059](images/img059.png)
Below All allowed.

![img060](images/img060.png)


![img061](images/img061.png)


Not allowed.(below)

![img062](images/img062.png)

![img063](images/img063.png)


---


![img064](images/img064.png)


When ‘int’ type variable is passed as argument “int overload will called”. Same as double and others.

---


## lambda Function:


![img065](images/img065.png)

![img066](images/img066.png)

* Return type is not important. If keep blank, compiler is gonna deduce its type by itself.
* Use ‘;’ after function body. Because lambda function is a statement.

![img067](images/img067.png)


![img068](images/img068.png)


![img069](images/img069.png)


Here if lambda function return something, it going to assign to variable ‘fun’.

Capture lists on lambda function: Capture list is a part of lambda function inside the square brackets which tells the lambda function, which variable from the surrounding scope it can use and how(like using a copy of a variable or references).
* When a lambda function capture values, it made a copy of that variable on the memory. So if that variable is changed later it will not effect on that lambda function. Lambda function retain the old value unless we use variable as reference. See below…

![img070](images/img070.png)


![img071](images/img071.png)


See when we use variable as reference:

![img072](images/img072.png)

![img073](images/img073.png)


If we print the addresses, we can clearly see that both(variable a, and lambda function variable a) variable have different addresses.

---

*** ”[=]” using this as capture list it will grab all variable from the surrounding scope. (To capture value)
*** ”[#]” using this as capture list it will grab all variable from the surrounding scope. (To capture as 
 
references)
*** using reference, all have same addresses.

---


## Function Template:

Function Template by value: Function Template is a mechanism in c++ to set up a blueprint for functions, But compiler going generate the actual code when it sees the function called. Means to avoid code repetition.


![img074](images/img074.png)


Here there are multiple function overload. They are doing the work. To minimise this type of multiple overload of same work. We can use Template.

![img075](images/img075.png)
“ T ” is a place holder for the data type function is going to receive as argument. But all argument data type have to be same(there is a room for not same data type). When compiler see, template function called. It going to look at the data type of arguments which are passing to function. Then compiler generate same function with that data type only when the function is called .
** can also pass string by argument.


Function templates are not c++ code. It just a function blueprint.

![img076](images/img076.png)

If data types are not same passing as argument, we can explicitly set the type with<double>. This basically tells the compiler to generate double/int etc. template instance function for this calling. And implicitly convert other type to determined type. In below example ”a” variable int type and will convert to double.
** We can see this internal conversion of function template on cppinsights.io.

![img077](images/img077.png)


This will give no error. Cause we explicitly tell to generate a double type template instance function. Otherwise, different type will not accept. Will throw an error.
If we use sizeof() to see size of the “re” variable. We can see is it double, int etc.

Template type parameter by references: Recall references procedure, template procedure. All same concept.

![img078](images/img078.png)


![img079](images/img079.png)
function overloaded. Cause calling
maximum(a,b); // this is used for both template with value and with reference. That’s why get confused.

---

Template Specialization: This is specially for “const char pointer” like:
const char* x=”asdf”;
for const char pointer regular method will not work. There is a special template mechanism for it.

![img080](images/img080.png)
This does not compare like others in template. See 18:50 Hr
Instead it use c++ template library function “strcmp” to compare. See on www.cppreference.com about strcmp.
In order to use template specialization we have to declare primary template like below…

![img081](images/img081.png)

![img082](images/img082.png)

In order to use template specialization we have to declare primary template like below…

![img083](images/img083.png)
Whole code:


![img084](images/img084.png)


## C++ 20:

Concept: Concept is a mechanism to set up constrain or restriction on template parameter of our function template. For example we can set that function to be called only integer and we call it something which isn’t ans integer, it will give a compiler error.

![img085](images/img085.png)


If we set double instead of int, this will compiler error. Cause we set “integral” type to accept as argument in function template.
These concepts are introduced in c++20. So use “-std=c++20” during compiling.

![img086](images/img086.png)


Concepts are introduced in c++20. Before that we can use this(below) inside function template. And set a custom message if condition does not meet.

![img087](images/img087.png)

Type Traits: Intro on C++11. A type trait is a small template “tool” that tells you something about a type, or transforms a type, at compile time. On above we are checking “T” is an integral or not by “is_integral<>”. Boolean value. Also Use this as requires. See below

![img088](images/img088.png)


We can use type traits on requires.

![img089](images/img089.png)


Some Type Traits:

![img090](images/img090.png)

Some ways to declare concepts:

![img091](images/img091.png)

![img092](images/img092.png)


Syntax 3 is only allowed for, when we use “auto”.(Below)

![img093](images/img093.png)


![img094](images/img094.png)


Example for Type Trait:
A type trait is a template utility in the C++ standard library (in <type_traits>) that allows you to query information about a type or transform a type at compile time.
Think of type traits as little “questions” or “tools” about types:
1. Is this type an integer?
2. Is this type const-qualified?
3. What happens if I remove a pointer from this type?
4. Are these two types the same?

![img095](images/img095.png)


Here the compiler removes the unused branch at compile time → no runtime cost.
Here without “constrxpr” if is checked at run time. So both branch(if, else) must compile because compiler doesn’t know which condition will be true.

But with “constexpr”
* if constexpr means the compiler chooses the branch at compile time.
* The unused branch is discarded before code generation — it’s as if it never existed. Means for (“print(42)”) compiler will keep only if part. And for (“print(3.14)”) compiler will keep else part.


![img096](images/img096.png)
*** Think f(42)=print(42)
Generated machine code for print(42) contains no trace of the "not integral" branch.
Generated machine code for print(3.14) contains no trace of the "integral" branch.
The compiler erases the irrelevant branch at compile time.
Constexpr- is a keyword in c++. That tells to evaluate the value in compile time.
See this from cppinsights.io comparing with and without “constexpr”

![img097](images/img097.png)


![img098](images/img098.png)
---------x----------


## Build own Concept/Custom concept:

Example 1:

![img099](images/img099.png)


Line- 9,10: Custom concept. Here we are setting function parameter have to integral type.
Line-13: function checks whether our parameter satisfy the concept. If one parameter is float it will give compiler error.
For int value the type trait (is_integral_v) is return true and concept is satisfied. And function template is gonna execute.
For double, float value we can use “is_floating_point<T>”.

Diff way to use concepts:

![img100](images/img100.png)

![img101](images/img101.png)


![img102](images/img102.png)

![img103](images/img103.png)


Example 2:

![img104](images/img104.png)


Line-10,11: requires 2 parameter which are multipliable. This will not give multiply of “a” ans “b” If pass (char) concepts will not satisfy. Error

Example 3: If we want “a” will be int and “b” will be double. See below. Use diff type name.

![img105](images/img105.png)


---

Deep dig into ‘Requires’ :

![img106](images/img106.png)

you can only put valid expressions involving the types/objects. requires doesn’t test boolean conditions — it just checks “is this expression well-formed?” check given expression is vakid or not.
Inside requires { ... }, each line is an expression requirement.
It only checks whether the expression is valid (well-formed) — not whether its value is true or false.


![img107](images/img107.png)


![img108](images/img108.png)


Here “sizeof(T)<=4” is simple requirement. Only check syntax.
Although b is double. It should give compiler error cause concepts does not meet(double size 8byte). It gives ans. Cause:
sizeof(T) <= 4 is always a valid expression (it produces a true value).
The compiler says “requirement satisfied” regardless of whether the condition is true or false.
It doesn’t enforce the size check.

![img109](images/img109.png)


This is correct way to set sizeof(). This will check conditions are true or false. And this will give error cause ‘b’ size is 8 byte. We set <=4.

Or we can use nested requirement(requires inside requires). See below(No error)

![img110](images/img110.png)


Example *: Using Logical operator...

![img111](images/img111.png)


Example **: 
![img112](images/img112.png)


Exit(): “exit(1)” terminate the whole program. So if this is also used in used in a function, it stop the entire program.

![img113](images/img113.png)

![img114](images/img114.png)


![img115](images/img115.png)
exit(0) → “Program ended successfully.”
exit(1) → “Program ended due to an error.” // abnormal termination of the program

---


*** If we pass an array to a function is pass its reference through pointer. Not a copy.


## OOP


Class: Class is a mechanism to build our own type to use them like we have been using built in type(int, double). Its like a blueprint to create object.
Object: An object is a real instance(copy) of that class. Like a actual car built from blueprint.

![img116](images/img116.png)


* Public means after “public” all parameter are accessible outside of the class.
* If public is not defined. Then in general all parameter are indicated to private. Means can’t access outside of the class. (Members of class are private by default).
* Public, private, protected are called access specifier.
* if public is not defined on above example. All member will be private. Line 19,20, 21 can’t write. Compiler will give error.
* Private members can be accessible from inside class.
* Objects(ob1) are run time data.
* Member variable should be set to private.

![img117](images/img117.png)


## Constructor:


![img118](images/img118.png)


Constructor are 2 type.
1. Default constructor. //Method have no parameter line: 13
2. Parameterized constructor. //Have parameter Line: 17


![img119](images/img119.png)


* This is how private members can be accessible inside class.
* If an object is declare default constructor will be called. Line: 13
* if not defined(default constructor), compiler will automatically generate default empty constructor.
Or inside main
“mycls ob1(12,22);” parameterized constructor will be called. Line: 17. default will not be called.
* If compiler sees any constructor, its not gonna generate default constructor.
* We can declare default constructor 2 ways; on line:13 & 16

![img120](images/img120.png)


## Setter & Getter:

Private members are not accessible from outside. Both are methods to modify or read member variable of a class.

---


ifndef:
![img121](images/img121.png)


Means this constant is define on any other file of the project and we are not sure, we cn use this. It says, if below code is not defined, I am defining here, else skip. Otherwise, if same things defined in many places, show error.

---


“::” Scope Resolution Operator: Used when a function of a class us defined on other file.

![img122](images/img122.png)
Here “Cylinder” constructor is belong to Cylinder class. We can use any function instead constructor.
But we have to mention function prototype inside the class. Like: Cylinder(double red_…..);

---


Manage class object by Pointer:
![img123](images/img123.png)


Here “ - >” is a dereferencing operator. Works like (*c2).findcir();
c2 pointer will be on stack memory but obj will be on heap.
Direct creating object creates on stack and with using pointer object will create on heap. Remember to release memory.

![img124](images/img124.png)


dangling pointer is dangerous. Holds old memory. So after deleting set c2=nullptr;


## Destructors:


![img125](images/img125.png)
Destructors are called by the compiler to destroy our objects.

![img126](images/img126.png)
When Destructor Called?
* When local stack objects goes out of scape then destructor is going to be called by compiler.
* When heap object is released with delete.
*** Destructor has no parameter.
*** Destructor does not called by compiler automatically for heap data. We have to release memory like line 32(below)
*** The compiler calls destructor for objects with automatic storage duration when they leave scope.
If I have 3 objects(d1,d2,d3), destructor will call 3 times. But in reverse order. ‘d3’ destructor will call 1st and d1 destructor in last.

![img127](images/img127.png)
Explained Below:
* “d1” is a local object. It destroyed when main() exits its scope after line 39 and before the program returns from main(line 41);
* ”d1” lives in stack. When main ends, C++ compiler automatically calls destructor. Memory released for ‘d1’ object.

![img128](images/img128.png)


In line 23 string_view

![img129](images/img129.png)
Pass an object by value: see 22:00:00 hr