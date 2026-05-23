# 📘 "C++: 31 hours long video of freecodecamp"

> **Emon_SUST** &nbsp;&nbsp;|&nbsp;&nbsp; 📞 01714076452

![C++](https://img.shields.io/badge/Language-C%2B%2B-blue?style=for-the-badge&logo=cplusplus) ![C++20](https://img.shields.io/badge/Standard-C%2B%2B20-informational?style=for-the-badge) ![FCC](https://img.shields.io/badge/Source-FreeCodeCamp-red?style=for-the-badge)

---


## ✨ Features:


supports data abstruction, means Data abstraction is a fundamental concept in computer science and tsoftware engineering that involves hiding the implementation details of data types and exposing only the essential features or behaviour to the outside world. Data abstraction is a powerful concept that facilitates the design, implementation, and maintenance of complex software systems by providing clear interfaces, encapsulating implementation details, promoting modularity, and supporting information hiding.


---


## 📝 Statement: A statement is a basic unit of computation in a C++ program. Ends with a semicolon(;).


	They are executed from top to bottom when program is run.


---

![](cpp_notes_images/01_statements_separator.png)

![](cpp_notes_images/02_input_space_separated.png)


### 📦 Variable: A piece of memory that used to store specific type of data.



### 🔢 Number System representation:


![](cpp_notes_images/03_number_system_representation.png)

> *** Modifier like signed, unsigned used integral data type as decimal number/ whole number. Can’t use for float, double(2.0, 2.5).


## 🔢 Float and Double:


![](cpp_notes_images/04_float_precision_digits.png)

For Float: 12345.6789-> 89will be garbage value. Cause precision 7 for Float. May print like: 12345.6725

> ** float a=123456789-> 89 will b garbage value. May print like: 12345.6745

![](cpp_notes_images/05_ieee754_float_representation.png)

![](cpp_notes_images/06_ieee754_code_example.png)

![](cpp_notes_images/07_setprecision_code.png)

cout<<setprecision(20);

![](cpp_notes_images/08_setprecision_output.png)

If we not set precision, the default precision will be 6 digits.(Total digits. Not after decimal point)

if we use “fixed” the with set precision(4), precision will be 4 after decimal point. Above a=12.1234;(ans)

But not using “fixed” precision will be 4 for total digits. Above a=12.12;(ans)

used for set precision. Library> #include<iomanip>

suffixes(like f, L): u // unsigned

ul // unsigned long

ll // long long


---

> **Booleans occupy 1byte/8bits in memory.

bool x=true; // or bool x=1;

bool y=false; // or bool y=0;

cout<<boolalpha; //used for printf true/false instead of 0/1

cout<<x<<” ”<<y;

will print true, false.


---


## 🔤 Character:


![](cpp_notes_images/09_char_boolean_examples.png)

![](cpp_notes_images/10_char_code.png)

![](cpp_notes_images/11_char_declaration.png)

> ** 31/10 means how many times 10 is gonna fit in 31. so ans is 3.

> * Relation Operator: > ,< , >=, <=

> * Logical Operator: &&, ||, !


---


## 🖨️ Manipulator:    https://en.cppreference.com/w/cpp/io/manip   //for more


> * std:flush: when we print something, it does not go directly to the terminal. It store somewhere called “buffer”. When buffer is full/ complete it goes to terminal. If use std:flush data directly goes to console/terminal instead of goes to buffer.

![](cpp_notes_images/12_manipulators_flush.png)

> *setw() : set width

cout<<right; // printf from right. 	Left for left alinement

![](cpp_notes_images/13_setw_right_alignment.png)

cout<<setfill(‘-’) // blank space fill with ‘-’

![](cpp_notes_images/14_setfill_example.png)

> *for finding max min numeric number limits data type can hold.

Need this> #include<limits>

![](cpp_notes_images/15_numeric_limits_include.png)


---


## ➗ #include<cmath> : abs(), pow(),  ceil(), log(), sqrt(), sin(), tan() etc https://en.cppreference.com/w/cpp/header/cmath


for log(): log(10) means loge(10). So have to fix the base as log10(10). E=2.71..

> * round(): 3.5 will make 4, and 3.49 will make 3.


---

![](cpp_notes_images/16_arithmetic_implicit_conversion.png)

if we take data type less than 4 byte and perform arithmatic operation compiler automatically convert it to 4 byte. This behavior also present on other operator like bitwise operator.(>>, <<)


---


## 🔀 flow control: if else, switch, ternary operator.


> *Switch: if we not use “Break”, the case which match, after that all case will execute and print every case value.

> * we can use int, char , double, enum etc but not string as case.


---

> * If we use “const” before array. We cant modify array elements.

> * a[ ]={2,3,7,5,2,3}; size(a) return the size of array. /Or sizeof(a)/sizeof(a[0]);

Enum: An enum is a special type that represents a group of constants (unchangeable values).

To create an enum, use the enum keyword, followed by the name of the enum, and separate the enum items with a comma.

![](cpp_notes_images/17_enum_declaration.png)

Enum is short for "enumerations", which means "specifically listed".

To access the enum, you must create a variable of it.

Inside the main() method, specify the enum keyword, followed by the name of the enum (Level) and then the name of the enum variable (myVar in this example):

![](cpp_notes_images/18_enum_main_variable.png)

By default, the first item (LOW) has the value 0, the second (MEDIUM) has the value 1, etc.

If you now try to print myVar, it will output 1, which represents MEDIUM:

![](cpp_notes_images/19_enum_print_output.png)

As you know, the first item of an enum has the value 0. The second has the value 1, and so on. To make more sense of the values, you can easily change them:

![](cpp_notes_images/20_enum_custom_values.png)

Note that if you assign a value to one specific item, the next items will update their numbers accordingly:

![](cpp_notes_images/21_enum_next_items_update.png)

Example:

![](cpp_notes_images/22_enum_example_full.png)


#### Why And When To Use Enums?


Enums are used to give names to constants, which makes the code easier to read and maintain. Use enums when you have values that you know aren't going to change, like month days, days, colours, deck of cards, etc.


## 🔗 Pointer


Pointer is special kind of variable.

int* int_num{}; or int* int_num; // will point to a integer type variable //initialise with null 					     // pointer(nulptr)

double* frac_num{}; // will point to a double type variable

int * int_num{}; // this initialisation with {} is going to initialise with special address means it is not 			//pointing any variable. Means initialize  with nullptr

int * int_num{nullptr}; // this pointer not pointer anywhere

> ** pointer of int, double, char etc all are same size. Cause they only store address.

Char *ptr{“Hello world”}; // Pointer will point to 1st character. Some compiler will not compile(MSVC). GCC will give warning and compile. A whole string is assigning to char type pointer. See:10:17:00

Cout<<ptr; // will print whole string.

Cout<<*ptr;// print 1st character ‘H’;

> *ptr=’B’;// this may give error. Cause compiler will think it as const char array.

 If want to modify. Don’t use character pointer, use array like: char msg[10]==”Hello world”;

or use const char *ptr{“Hello world”};  // no warning. Can’t modify also.

Dereferencing pointer: reading something(value) on the address of the pointer. Cout<<*ptr;

string with pointer: char* p_msg= “Hello World!”; // the pointer will point to the 1st character of string

> *this will compile with warning. Use const char* p_msg= “Hello World!”;

printf p_msg will print whole string. But using dereferencing will print 1st character(*p_msg).

> *** without const it gives warning/refuse to compile cause compiler is going to convert string into char array of constant char. What we are using is points to that is not a const char pointer. So pointer here might be used to try or modify data. That’s why it refuse unless using const.

Check at 10:17min

int *ptr;// contain junk address

int a=12;

> *ptr=&a;

uninitialized pointer contain junk address. Assigning a value to it(*ptr=12)May cause error. Could be point to a memory which is used by OS. May cause disaster.

Use this: int a; int *ptr=&a;

![](cpp_notes_images/23_pointer_uninitialized_fix.png)


## 🗺️ Memory Map


When we run a program it runs on RAM. Various program of OS or other is running on memory.

![](cpp_notes_images/24_memory_map_programs_ram.png)

![](cpp_notes_images/25_memory_map_virtual.png)

This process thinks it own 0~2N  amount of memory which is virtual memory.

When we run a program it is going to go through a CPU section called memory management unit(MMU).

![](cpp_notes_images/26_mmu_mapping.png)

MMU really does is, helps us mapping between the memory map in ur program and the real thing we have in RAM.

If we run few program, they are going to go through MMU and MMU is going assign them real section on RAM

![](cpp_notes_images/27_mmu_program_sections.png)

> * Since program thinks it 2n -1 memory, The MMU is going to transform between the idea the program has and the RAM we have(assigned memory by MMU).

> * The memory map/Structure of program is standard format defined by OS. That’s why we can’t run directly window program on Linux.

> *Memory map is divided into a lot parts

![](cpp_notes_images/28_memory_map_parts.png)

> * STACK: Local variable stores on stack section.

> * print, statement, function calls others store on stack section.

> * TEXT:Actual binary load on Text so that CPU can execute it.

> * HEAP:Additional memory when we run out of stack memory also to  make things better for program, Used for run time.


## 💾 Dynamic Memory Allocation


![](cpp_notes_images/29_dynamic_memory_allocation.png)

2nd point- full Control:  when declare a variable a=23; in stack it remove when scope is over. Developer doesn’t have full control. But in heap developer have full control when a variable comes to work and dies.

 >> 10:41 min

![](cpp_notes_images/30_heap_pointer_setup.png)

> *set up a pointer which point to heap memory.

After initializing a pointer with nullptr. When p_number4=new int execute the OS is allocate a memory on heap. Variables are usually stores on stack section. It removes when variable containing scope will over. But if we allocate a memory on heap by “p_number4=new int;” . This memory will live though its scope is over. It will stay until return it to operating system. To return:

![](cpp_notes_images/31_new_int_allocation.png)

Use ‘delete’ to return memory to the  operating system. After return reset pointer to ‘nullptr’ is good to make it clear that no valid data pointer is pointing.

> * Using ‘delete’ remove the allocated heap memory which is pointed. Not the pointer. If pointing to ‘nullptr’, delete will do nothing.

> *** Always remember to release memory.

> *Dangling Pointer: A pointer that doesn’t point to a valid memory address. Trying to dereferencing and using a dangling pointer  will results in undefined behaviour.

How dangling pointer create:

1. Uninitialized pointer.

2. Delete pointer

3. Multiple pointer points to same memory.

Solution:

1. Initialize pointer. Either with valid address or nullptr.

2. Reset pointer after delete.(Either with valid address or nullptr.)

3. For multiple pointer point to same address, make sure master pointer is clear/ reset.

> *** Always check if pointer is nullptr or not by if-else.

‘New’ fails:

When allocating an array with pointer with huge size(1000000000000000000). It may fails and program can crash. We can use exception mechanism or ‘nothrow’ to prevent crashing.

![](cpp_notes_images/32_new_array_fail.png)

Both allocation (with for loop or without) fail.

> * Solve with ‘exception mechanism’:

![](cpp_notes_images/33_exception_mechanism.png)

With ‘exception’ we can catch the problem. What is called ‘handle’ in the problem. Suppose we are going to set up color and color fails. UI(interface) may show black and white. But program will keep running “what()”  function will show the error.

> *with ‘nothrow’: If “new” fails, we are going to get “nullptr” stored.

![](cpp_notes_images/34_nothrow_example.png)

For clear understanding see

https://www.youtube.com/watch?v=uoCuMTzD9AE&list=PLgH5QX0i9K3q0ZKeXtF--CZ0PdH1sSbYL&index=90 // anisul islam lecture 92. Exception handling


### 🛡️ NULL pointer safety:


![](cpp_notes_images/35_null_pointer_safety_if.png)

check if null or not.

![](cpp_notes_images/36_null_pointer_safety_or.png)

![](cpp_notes_images/37_null_ptr_boolean_implicit.png)

> * After use delete set pointer to nullptr for safety.


---


### 💧 Memory Leaks:


![](cpp_notes_images/38_memory_leaks_example.png)

![](cpp_notes_images/39_memory_leak_double_alloc.png)

Should delete 1st then allocate 2nd.

![](cpp_notes_images/40_delete_then_allocate.png)

After local scope is over, pointer is gonna die, but allocated memory will remain and loose access.

These memory leaks may causes program crash.


### 📊 Dynamic array: Array stores on the heap.


![](cpp_notes_images/41_dynamic_array_heap.png)

![](cpp_notes_images/42_dynamic_array_code.png)

Release Memory:

![](cpp_notes_images/43_release_memory_delete.png)

Dynamic arrays are created at run time not compile time.

![](cpp_notes_images/44_dynamic_array_explanation.png)

![](cpp_notes_images/45_dynamic_array_explanation2.png)

![](cpp_notes_images/46_dynamic_array_explanation3.png)

Reference: A reference is an alias (another name) for an existing variable. It does not create a new variable or occupy memory, it just gives another way to access the same memory. Doesn’t hold addresses as pointer.

![](cpp_notes_images/47_reference_alias_intro.png)

If we change reference value or variable value, both contribute same changes.

> ** “&ref” and “&s” both has same memory address.

![](cpp_notes_images/48_reference_same_address.png)

![](cpp_notes_images/49_pointer_reassign_vs_reference.png)

![](cpp_notes_images/50_pointer_vs_reference_code.png)

Here ‘S and ref’ value will changes to 12.

Use case: *if want to modify original variable inside a function. This save memories.

![](cpp_notes_images/51_reference_modify_in_function.png)

> * Return reference by function to a local or global variable.

![](cpp_notes_images/52_return_reference_function.png)

![](cpp_notes_images/53_return_reference_example.png)

> * Using “const” before reference makes the variable unchangeable. This constant only applies to reference. Not variable. Can’t changes variable value with “const reference”. But variable itself can changes its value.

![](cpp_notes_images/54_const_reference_example.png)

Value will changes to 12.


---

> *** size(), sizeof() function return the size. But for character array it includes ‘null’ . But for string  size() don’t count null.

> *** strlen() is used for character array. Not for string.

		char *a=”asdf”;     // this is string literal. Not modifiable.

		Char a[]=”asdf”;   // this is character array. Modifiable. Use stack memory.

Using “const” is safe in string literal.

> ***String literal is actually a character array. When we assign it to “const char * ”, it automatically converts into a pointer to 1st element. String has not fixed amount of memory, cause it internally implemented as a class and it stores its data as const char pointer.

	Const char *msg=”Hello I am here.”;

![](cpp_notes_images/55_string_char_pointer_const.png)

Character array lives on read only memory. Can’t modify.


---

swap 2 number.

1. a=a+b;     b=a-b;    a=a-b;

2. a=a^b;      b=a^b;   a=a^b;


---


### ↩️ Returning from function as Reference: Usually function returns values(int, char etc). But sometime compilers are smart enough that that return reference instead of values. Avoid copies. See below


![](cpp_notes_images/56_swap_numbers_xor.png)

![](cpp_notes_images/57_function_overload_examples.png)

![](cpp_notes_images/58_function_overload_int_double.png)

      Output:

Here both addresses are same. Its returns the reference. Using reference mechanism.


---


## ⚙️ Function Overloaded: Means we can declare multiple function with same name in the same scope, but with different parameter lists. Like parameter type(int, double, float).


![](cpp_notes_images/59_function_overload_allowed1.png)

![](cpp_notes_images/60_function_overload_allowed2.png)

![](cpp_notes_images/61_function_overload_allowed3.png)

Not allowed.(below)

![](cpp_notes_images/62_function_overload_not_allowed1.png)

![](cpp_notes_images/63_function_overload_not_allowed2.png)


---

![](cpp_notes_images/64_when_overload_called.png)

When ‘int’ type variable is passed as argument “int overload will called”. Same as double and others.


---


### ⚡ lambda Function:


![](cpp_notes_images/65_lambda_syntax.png)

![](cpp_notes_images/66_lambda_example_full.png)

> * Return type is not important. If keep blank, compiler is gonna deduce its type by itself.

> * Use ‘;’ after function body. Because lambda function is a statement.

![](cpp_notes_images/67_lambda_with_return.png)

![](cpp_notes_images/68_lambda_capture_intro.png)

![](cpp_notes_images/69_lambda_capture_variable.png)

Here  if lambda function return something, it going to assign to variable ‘fun’.

Capture lists on lambda function: Capture list is a part of lambda function inside the square brackets which tells the lambda function, which variable from the surrounding scope it can use and how(like using a copy of a variable or references).

> * When a lambda function capture values, it made a copy of that variable on the memory. So if that variable is changed later it will not effect on that lambda function. Lambda function retain the old value unless we use variable as reference. See below…

![](cpp_notes_images/70_lambda_capture_by_value.png)

![](cpp_notes_images/71_lambda_capture_value_copy.png)

See when we use variable as reference:

![](cpp_notes_images/72_lambda_capture_by_reference.png)

![](cpp_notes_images/73_lambda_reference_address.png)

If we print the addresses, we can clearly see that both(variable a, and lambda function variable a) variable have different addresses.


---

> *** ”[=]” using this as capture list it will grab all variable from the surrounding scope. (To capture value)

> *** ”[#]” using this as capture list it will grab all variable from the surrounding scope. (To capture as 	       	references)

> *** using reference, all have same addresses.


---


## 📐 Function Template:



### 📐 Function Template by value: Function Template is a mechanism in c++ to set up a blueprint for functions, But compiler going generate the actual code when it sees the function called. Means to avoid code repetition.


![](cpp_notes_images/74_function_template_intro.png)

Here there are multiple function overload. They are doing the work. To minimise this type of multiple overload of same work. We can use Template.

![](cpp_notes_images/75_function_template_blueprint.png)

> ** can also pass string by argument.

Function templates are not c++ code. It just a function blueprint.

![](cpp_notes_images/76_function_template_code.png)

If data types are not same passing as argument, we can  explicitly set the type with<double>. This basically tells the compiler to generate double/int etc. template instance function for this calling. And implicitly convert other type to determined type. In below example ”a” variable int type and will convert to double.

> ** We can see this internal conversion of function template on cppinsights.io.

![](cpp_notes_images/77_function_template_explicit_type.png)

This will give no error. Cause we explicitly tell to generate a double type template instance function. Otherwise, different type will not accept. Will throw an error.

If we use sizeof() to see size of the “re” variable. We can see is it double, int etc.

Template type parameter by references: Recall references procedure, template procedure. All same concept.

![](cpp_notes_images/78_template_by_reference.png)

![](cpp_notes_images/79_template_overload_confusion.png)

maximum(a,b); // this is used for both template with value and with reference. That’s why get confused.


---

 Template Specialization: This is specially for “const char pointer” like:

	const char* x=”asdf”;

for const char pointer regular method will not work. There is a special template mechanism for it.

![](cpp_notes_images/80_template_specialization_const_char.png)

Instead it use c++ template library function “strcmp” to compare. See on www.cppreference.com about strcmp.

In order to use template specialization we have to declare primary template like below…

![](cpp_notes_images/81_template_specialization_primary.png)

![](cpp_notes_images/82_template_specialization_in_order.png)

In order to use template specialization we have to declare primary template like below…

![](cpp_notes_images/83_template_specialization_code1.png)

![](cpp_notes_images/84_template_specialization_code2.png)


## 🆕 C++ 20:


Concept: Concept is a mechanism to set up constrain or restriction on template parameter of  our function template. For example we can set that function to be called only integer and we call it something which isn’t ans integer, it will give a compiler error.

![](cpp_notes_images/85_concept_integral_example.png)

If we set double instead of int, this will compiler error. Cause we set “integral” type to accept as argument in function template.

These concepts are introduced in c++20. So use “-std=c++20” during compiling.

![](cpp_notes_images/86_concept_std_c20_compile.png)

Concepts are introduced in c++20. Before that we can use this(below) inside function template. And set a custom message if condition does not meet.

![](cpp_notes_images/87_concept_before_c20_static_assert.png)

Type Traits: Intro on C++11. A type trait is a small template “tool” that tells you something about a type, or transforms a type, at compile time. On above we are checking “T” is an integral or not by “is_integral<>”. Boolean value. Also Use this as requires. See below

![](cpp_notes_images/88_type_traits_requires_example.png)

We can use type traits on requires.

![](cpp_notes_images/89_type_traits_in_requires.png)

Some Type Traits:

![](cpp_notes_images/90_some_type_traits.png)

Some ways to declare concepts:

![](cpp_notes_images/91_concept_declaration_ways1.png)

![](cpp_notes_images/92_concept_declaration_ways2.png)

Syntax 3 is only allowed for, when we use “auto”.(Below)

![](cpp_notes_images/93_concept_syntax3_auto.png)

![](cpp_notes_images/94_concept_syntax3_auto_example.png)

Example for Type Trait:

A type trait is a template utility in the C++ standard library (in <type_traits>) that allows you to query information about a type or transform a type at compile time.

Think of type traits as little “questions” or “tools” about types:

1. Is this type an integer?

2. Is this type const-qualified?

3. What happens if I remove a pointer from this type?

4. Are these two types the same?

![](cpp_notes_images/95_type_traits_example_full.png)

Here the compiler removes the unused branch at compile time → no runtime cost.

Here without “constrxpr” if is checked at run time. So both branch(if, else) must compile because compiler doesn’t know which condition will be true.

But with “constexpr”

> * if constexpr means the compiler chooses the branch at compile time.

> * The unused branch is discarded before code generation — it’s as if it never existed. Means for (“print(42)”) compiler will keep only  if part. And for (“print(3.14)”) compiler will keep else part.

![](cpp_notes_images/96_constexpr_if_branch_selection.png)

Generated machine code for print(42) contains no trace of the "not integral" branch.
Generated machine code for print(3.14) contains no trace of the "integral" branch.

The compiler erases the irrelevant branch at compile time.

Constexpr- is a keyword in c++. That tells to evaluate the value in compile time.

See this from cppinsights.io  comparing with and without “constexpr”

![](cpp_notes_images/97_constexpr_cppinsights_with.png)

![](cpp_notes_images/98_constexpr_cppinsights_without.png)


### 🏗️ Build own Concept/Custom concept:


Example 1:

![](cpp_notes_images/99_custom_concept_example1.png)

Line- 9,10: Custom concept. Here we are setting function parameter have to integral type.

Line-13: function checks whether our parameter satisfy the concept. If one parameter is float it will give compiler error.

For int value the type trait (is_integral_v) is return true and concept is satisfied. And function template is gonna execute.

For double, float value we can use “is_floating_point<T>”.

Diff way to use concepts:

![](cpp_notes_images/100_custom_concept_diff_ways1.png)

![](cpp_notes_images/101_custom_concept_diff_ways2.png)

![](cpp_notes_images/102_custom_concept_diff_ways3.png)

![](cpp_notes_images/103_custom_concept_diff_ways4.png)

Example 2:

![](cpp_notes_images/104_custom_concept_example2_multipliable.png)

Line-10,11: requires 2 parameter which are multipliable. This will not give multiply of “a” ans “b” If pass (char)  concepts will not satisfy. Error

Example 3: If we want “a” will be int and “b” will be double. See below. Use diff type name.

![](cpp_notes_images/105_custom_concept_example3_two_types.png)


---

Deep dig into ‘Requires’ :

![](cpp_notes_images/106_requires_deep_dive_simple.png)

 you can only put valid expressions involving the types/objects. requires doesn’t test boolean conditions — it just checks “is this expression well-formed?” check given expression is vakid or not.

Inside requires { ... }, each line is an expression requirement.

It only checks whether the expression is valid (well-formed) — not whether its value is true or false.

![](cpp_notes_images/107_requires_sizeof_always_valid.png)

![](cpp_notes_images/108_requires_sizeof_invalid_check.png)

Here “sizeof(T)<=4” is simple requirement. Only check syntax.

Although b is double. It should give compiler error cause concepts does not meet(double size 8byte). It gives ans. Cause:

sizeof(T) <= 4 is always a valid expression (it produces a true value).

The compiler says  “requirement satisfied” regardless of whether the condition is true or false.

It doesn’t enforce the size check.

![](cpp_notes_images/109_requires_sizeof_correct_way.png)

This is correct way to set sizeof(). This will check conditions are true or false. And this will give error cause ‘b’ size is 8 byte. We set <=4.

Or we can use nested requirement(requires inside requires). See below(No error)

![](cpp_notes_images/110_requires_nested_requirement.png)

Example *: Using Logical operator...

![](cpp_notes_images/111_requires_logical_operator.png)

![](cpp_notes_images/112_requires_example_double_star.png)

Exit(): “exit(1)” terminate the whole program. So if this is also used in used in a function, it stop the entire program.

![](cpp_notes_images/113_exit_function_example.png)

![](cpp_notes_images/114_exit_code_example.png)

![](cpp_notes_images/115_exit_codes_explanation.png)

exit(1) → “Program ended due to an error.” // abnormal termination of the program


---

> *** If we pass an array to a function is pass its reference through pointer. Not a copy.


## 🏛️ OOP



### 🏗️ Class: Class is a mechanism to build our own type to use them like we have been using built in type(int, double). Its like a blueprint to create object.



### 📦 Object: An object is a real instance(copy) of that class. Like a actual car built from blueprint.


![](cpp_notes_images/116_class_blueprint_example.png)

> * Public means after “public” all parameter are accessible outside of the class.

> * If public is not defined. Then in general all parameter are indicated to private. Means can’t  access outside of the class. (Members of class are private by default).

> * Public, private, protected are called access specifier.

> * if public is not defined on above example. All member will be private. Line 19,20, 21 can’t write. Compiler will give error.

> * Private members can be accessible from inside class.

> * Objects(ob1) are run time data.

> * Member variable should be set to private.

![](cpp_notes_images/117_class_private_members.png)


### 🔧 Constructor:


![](cpp_notes_images/118_constructor_types.png)

Constructor are 2 type.

1. Default constructor.  //Method have no parameter line: 13

2. Parameterized constructor. //Have parameter Line: 17

![](cpp_notes_images/119_constructor_parameterized.png)

> * This is how private members can be accessible inside class.

> * If an object is declare default constructor will be called. Line: 13

> * if not defined(default constructor), compiler will automatically generate default empty constructor.

Or inside main

“mycls ob1(12,22);” parameterized constructor will be called. Line: 17. default will not be called.

> * If compiler sees any constructor, its not gonna generate default constructor.

> * We can declare default constructor 2 ways; on line:13 & 16

![](cpp_notes_images/120_constructor_default_declaration.png)


### 🔒 Setter & Getter:


Private members are not accessible from outside. Both are methods to modify or read member variable of a class.


---

![](cpp_notes_images/121_ifndef_include_guard.png)

Means this constant is define on any other file of the project and we are not sure, we can use this. It says, if below code is not defined, I am defining here, else skip. Otherwise, if same things defined in many places, show error.


---

“::” Scope Resolution Operator: Used when a function of a class us defined on other file.

![](cpp_notes_images/122_scope_resolution_operator.png)

But we have to mention function prototype inside the class. Like: Cylinder(double red_…..);


---

![](cpp_notes_images/123_pointer_object_management.png)

Here “ - >” is a dereferencing operator. Works like (*c2).findcir();

c2 pointer will be on stack memory but obj will be on heap.

Direct creating object creates on stack and with using pointer object will create on heap. Remember to release memory.

![](cpp_notes_images/124_pointer_vs_stack_object.png)

dangling pointer is dangerous. Holds old memory. So after deleting set c2=nullptr;


### 💥 Destructors:


![](cpp_notes_images/125_destructor_declaration.png)

![](cpp_notes_images/126_destructor_when_called.png)

> * When local stack objects goes out of scape then destructor is going to be called by compiler.

> * When heap object is released with delete.

> *** Destructor has no parameter.

> *** Destructor does not called by compiler automatically for heap data. We have to release memory like line 32(below)

> *** The compiler calls destructor for objects with automatic storage duration when they leave scope.

If I have 3 objects(d1,d2,d3), destructor will call 3 times. But in reverse order. ‘d3’ destructor will call 1st and d1 destructor in last.

![](cpp_notes_images/127_destructor_order_explained.png)

> * “d1” is a local object. It destroyed when main() exits its scope after line 39 and before the program returns from main(line 41);

> * ”d1” lives in stack. When main ends, C++ compiler automatically calls destructor. Memory released for ‘d1’ object.

![](cpp_notes_images/128_destructor_d1_stack.png)

In line 23 string_view

![](cpp_notes_images/129_string_view_in_destructor.png)

![](cpp_notes_images/130_string_view_code.png)

Diff Bet string_view & string:

![](cpp_notes_images/131_string_view_vs_string.png)

![](cpp_notes_images/132_string_view_vs_string_code1.png)

![](cpp_notes_images/133_string_view_vs_string_code2.png)

Pass an object by value: see 22:00:00 hr

“this” Pointer:  ‘this’ is a special kind of pointer, maintain by c++ to manipulate the current object. This ‘this’ pointer contains the address of the current object.

![](cpp_notes_images/134_this_pointer_intro.png)

//"this" will print current object address

![](cpp_notes_images/135_this_pointer_print_address.png)

Not exactly pointing to the current object member(above).


#### Chained call using Pointer:


![](cpp_notes_images/136_chained_call_pointer.png)


#### Chained call using Reference:


![](cpp_notes_images/137_chained_call_reference.png)

Here ‘const’ is important to include.

What happen in line: 33

![](cpp_notes_images/138_chained_call_line33.png)


### ⚖️ Struct Vs Classes: Struct is another way to  define classes. Differences:


![](cpp_notes_images/139_struct_vs_class_differences.png)

![](cpp_notes_images/140_struct_vs_class_table.png)

So We can use struct when we have public members. But both are almost same. We can use anyone.


### 📏 Size of the class objects: Size of the class objects depends on the member of the class, not functions.


![](cpp_notes_images/141_class_object_size_string.png)

Here, string size is 32 byte whether I put no character or put millions of character. It will remain same.  We are not getting memory which occupy by characters, but getting the fixed size of the string object itself in the memory. It includes internal pointers, metadata(like length, capacity) and other housekeeping data.

![](cpp_notes_images/142_string_dynamic_heap_storage.png)

![](cpp_notes_images/143_string_sso_small_string.png)

![](cpp_notes_images/144_string_size_explanation.png)

Object size:

![](cpp_notes_images/145_object_size_example.png)

Here object size should be 44 byte. But Actual size is 48. cause, Alignment rule

![](cpp_notes_images/146_object_alignment_rule.png)

The total object size must be a multiple of the largest alignment (here: 8 bytes)

so there will 4 byte padding after 4 byte integer memory. See memory layout: below

![](cpp_notes_images/147_object_padding_layout.png)

Here Offset is the byte position of a member inside an object, measured from the object start.

For functions:

![](cpp_notes_images/148_functions_no_size_contribution.png)


## 🧬 Inheritance: Inheritance in C++ is a mechanism that allows a new class (derived class) to inherit properties and behaviours (methods) from an existing class (base class), promoting code reuse and creating a hierarchical relationship between classes.


When a class inherits another class, it gets all the accessible members of the parent class, and the child class can also redefine (override) or add new functionality to them.

![](cpp_notes_images/149_inheritance_example.png)

 Public, private, protected are access specifier.

![](cpp_notes_images/150_inheritance_access_specifiers.png)

in the above example, player class inherits all public members of human. But can’t access private. That’s why we only can print ‘age’ variable. Also passing string through player object(”motaher”, “emon”) constructor will be unused. We have to use public setter & getter.

> ***Protected member: Sometime we may want that members of base class has to be accessible from derived class but still be inaccessible from outside. In that case use those member as protected member. Below:

![](cpp_notes_images/151_inheritance_protected_member.png)

> ***Base class access specifier:

![](cpp_notes_images/152_inheritance_base_access_specifier.png)

Here” Public” is base class access specifier. This is public inheritance. This can be private/protected.

This tell how accessible the base class members to derived class.

![](cpp_notes_images/153_inheritance_accessibility_table.png)


#### Public Inheritance:


1. Anything public in base class, will remain public in derived class.

2. Anything protected in base class, will remain protected in derived class.

3. Private members are never inherited. Derived class can’t access.

Others(private, protected) we can derived from our assumption.

![](cpp_notes_images/154_inheritance_public_rules.png)

![](cpp_notes_images/155_inheritance_private_protected.png)

![](cpp_notes_images/156_inheritance_access_summary.png)

