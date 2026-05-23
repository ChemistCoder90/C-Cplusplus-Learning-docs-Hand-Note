# 📘 C++ Notes — FreeCodeCamp 31-Hour Course

> **Author:** Emon — Shahjalal University of Science and Technology (SUST)  
> **Source:** [FreeCodeCamp C++ Full Course (31 hrs)](https://www.youtube.com/watch?v=8jLOx1hD3_o)  
> **Contact:** 01714076452

![C++](https://img.shields.io/badge/Language-C%2B%2B-blue?style=for-the-badge&logo=cplusplus)
![Standard](https://img.shields.io/badge/Standard-C%2B%2B20-informational?style=for-the-badge)
![Status](https://img.shields.io/badge/Notes-In%20Progress-yellow?style=for-the-badge)

---

## 📑 Table of Contents

- [Statements](#-statements)
- [Variables & Data Types](#-variables--data-types)
- [Manipulators](#-manipulators)
- [Math Functions](#-math-functions)
- [Flow Control](#-flow-control)
- [Arrays & Enums](#-arrays--enums)
- [Pointers](#-pointers)
- [References](#-references)
- [Strings & Character Arrays](#-strings--character-arrays)
- [Functions](#-functions)
- [C++20 Concepts & Type Traits](#-c20-concepts--type-traits)
- [OOP](#-oop--object-oriented-programming)
- [Inheritance](#-inheritance)

---

## 📝 Statements

A **statement** is the basic unit of computation in a C++ program. Ends with `;`. Executed top to bottom.

![](cpp_notes_images/01_statements_separator.png)

---

## 📦 Variables & Data Types

### Input (space-separated)

![](cpp_notes_images/02_input_space_separated.png)

### Number System Representation

![](cpp_notes_images/03_number_system_representation.png)

> ⚠️ Modifiers like `signed`/`unsigned` only work with integral types. Cannot use with `float` or `double`.

---

### Float & Double

**Precision includes digits before the decimal point.** `12547.325` → `12547` is part of the 7-digit count.

![](cpp_notes_images/04_float_precision_digits.png)

Floating-point memory representation is based on [IEEE 754](https://www.youtube.com/watch?v=8afbTaA-gOQ&t=181s) — NOT the same as decimal.

![](cpp_notes_images/05_ieee754_float_representation.png)

![](cpp_notes_images/06_ieee754_code_example.png)

![](cpp_notes_images/07_setprecision_code.png)

> Default precision = **6 digits** (total). Use `fixed` to make it digits after decimal point.

![](cpp_notes_images/08_setprecision_output.png)

**Suffixes:** `u` = unsigned, `ul` = unsigned long, `ll` = long long

---

### Booleans

`bool` occupies **1 byte / 8 bits** in memory.

![](cpp_notes_images/09_char_boolean_examples.png)

![](cpp_notes_images/10_char_code.png)

---

### Characters

![](cpp_notes_images/11_char_declaration.png)

---

## 🖨️ Manipulators

> Reference: [cppreference — Manipulators](https://en.cppreference.com/w/cpp/io/manip)

`std::flush` — sends buffer directly to console instead of waiting for buffer to fill.

![](cpp_notes_images/12_manipulators_flush.png)

`setw()` + right/left alignment:

![](cpp_notes_images/13_setw_right_alignment.png)

`setfill()` — fill blank space with a custom character:

![](cpp_notes_images/14_setfill_example.png)

**Numeric Limits** — `#include<limits>`:

![](cpp_notes_images/15_numeric_limits_include.png)

> Reference: [cppreference — numeric_limits](https://en.cppreference.com/w/cpp/types/numeric_limits)

**Arithmetic implicit conversion** — data types less than 4 bytes are auto-promoted to 4 bytes during arithmetic (also applies to bitwise operators):

![](cpp_notes_images/16_arithmetic_implicit_conversion.png)

---

## 🔢 Math Functions

`#include<cmath>` — `abs()`, `pow()`, `ceil()`, `log()`, `sqrt()`, `sin()`, `tan()` etc.

> ⚠️ `log(10)` = logₑ(10). Use `log10(10)` for base-10. `round(3.5)` → `4`, `round(3.49)` → `3`.

> Reference: [cppreference — cmath](https://en.cppreference.com/w/cpp/header/cmath)

---

## 🔀 Flow Control

`if/else`, `switch`, ternary operator.

> ⚠️ Without `break` in switch, all following cases execute after a match. Cases accept `int`, `char`, `enum` — **not** `string`.

---

## 📋 Arrays & Enums

> Using `const` before an array prevents modifying its elements.  
> `sizeof(a)/sizeof(a[0])` gives array size.

### Enum

An enum is a special type representing a group of **named constants**.

![](cpp_notes_images/17_enum_declaration.png)

Access via a variable of the enum type:

![](cpp_notes_images/18_enum_main_variable.png)

By default: first item = `0`, second = `1`, etc. Printing `myVar` (MEDIUM):

![](cpp_notes_images/19_enum_print_output.png)

You can assign custom values:

![](cpp_notes_images/20_enum_custom_values.png)

Assigning one item updates subsequent items accordingly:

![](cpp_notes_images/21_enum_next_items_update.png)

Full example:

![](cpp_notes_images/22_enum_example_full.png)

**Use enums for:** month days, days of week, colours, card suits — values that won't change.

---

## 🔗 Pointers

A pointer is a special variable that stores a **memory address**.

```cpp
int*    int_num{};       // initialized to nullptr
double* frac_num{};
int*    int_num{nullptr};
```

All pointer types are the **same size** — they only store addresses.

**Correct usage:**

![](cpp_notes_images/23_pointer_uninitialized_fix.png)

> ⚠️ Uninitialized pointer contains a junk address — assigning a value may corrupt OS memory.

---

### Memory Map

When a program runs it goes through the **MMU (Memory Management Unit)** which maps virtual addresses to real RAM.

![](cpp_notes_images/24_memory_map_programs_ram.png)

![](cpp_notes_images/25_memory_map_virtual.png)

![](cpp_notes_images/26_mmu_mapping.png)

![](cpp_notes_images/27_mmu_program_sections.png)

Memory map is divided into parts:

![](cpp_notes_images/28_memory_map_parts.png)

- **STACK** — local variables, function calls
- **TEXT** — actual binary loaded for CPU execution
- **HEAP** — dynamic/runtime memory

> The memory map format is defined by the OS — that's why Windows `.exe` won't run on Linux directly.

---

### Dynamic Memory Allocation

![](cpp_notes_images/29_dynamic_memory_allocation.png)

![](cpp_notes_images/30_heap_pointer_setup.png)

After `p_number = new int`, OS allocates heap memory. This memory lives beyond scope — until you `delete` it:

![](cpp_notes_images/31_new_int_allocation.png)

> Always `delete` then reset to `nullptr`.

**`new` failure — allocating huge array:**

![](cpp_notes_images/32_new_array_fail.png)

**Solve with exception mechanism:**

![](cpp_notes_images/33_exception_mechanism.png)

**Solve with `nothrow`** — returns `nullptr` instead of crashing:

![](cpp_notes_images/34_nothrow_example.png)

> 📺 [Anisul Islam — Exception Handling (Lecture 92)](https://www.youtube.com/watch?v=uoCuMTzD9AE&list=PLgH5QX0i9K3q0ZKeXtF--CZ0PdH1sSbYL&index=90)

**NULL pointer safety:**

![](cpp_notes_images/35_null_pointer_safety_if.png)

![](cpp_notes_images/36_null_pointer_safety_or.png)

Pointer address implicitly converts to boolean (`null == 0`):

![](cpp_notes_images/37_null_ptr_boolean_implicit.png)

---

### Dangling Pointers

A pointer that doesn't point to a valid memory address. Dereferencing → **undefined behaviour**.

**Causes:** uninitialized pointer, deleted pointer, multiple pointers to same memory.

**Solution:** Always initialize. Reset after `delete`. For multiple pointers, reset master pointer. Always check `nullptr` before use.

---

### Memory Leaks

![](cpp_notes_images/38_memory_leaks_example.png)

Double allocation without releasing first:

![](cpp_notes_images/39_memory_leak_double_alloc.png)

> Pointer changes to 2nd allocation — access to 1st memory (55) is lost!

Always `delete` first, then allocate again:

![](cpp_notes_images/40_delete_then_allocate.png)

After scope ends, pointer dies but heap memory remains and becomes inaccessible → crashes.

---

### Dynamic Arrays

Array stored on the heap:

![](cpp_notes_images/41_dynamic_array_heap.png)

![](cpp_notes_images/42_dynamic_array_code.png)

**Releasing memory:**

![](cpp_notes_images/43_release_memory_delete.png)

Dynamic arrays are created at **runtime**, not compile time.

![](cpp_notes_images/44_dynamic_array_explanation.png)

![](cpp_notes_images/45_dynamic_array_explanation2.png)

![](cpp_notes_images/46_dynamic_array_explanation3.png)

---

## 🔄 References

A reference is an **alias** for an existing variable. Does not occupy new memory or hold an address like a pointer.

![](cpp_notes_images/47_reference_alias_intro.png)

Both `&ref` and `&s` have the **same memory address**:

![](cpp_notes_images/48_reference_same_address.png)

**Pointer can be reassigned; reference cannot:**

![](cpp_notes_images/49_pointer_reassign_vs_reference.png)

![](cpp_notes_images/50_pointer_vs_reference_code.png)

**Use case — modify original variable inside a function (saves memory):**

![](cpp_notes_images/51_reference_modify_in_function.png)

**Return reference from function:**

![](cpp_notes_images/52_return_reference_function.png)

![](cpp_notes_images/53_return_reference_example.png)

Both addresses are the same — reference returned, no copy made.

**`const` reference** — makes variable unchangeable via reference (but the variable itself can still change):

![](cpp_notes_images/54_const_reference_example.png)

---

## 🔤 Strings & Character Arrays

![](cpp_notes_images/55_string_char_pointer_const.png)

```cpp
char *a = "asdf";    // string literal — NOT modifiable
char a[] = "asdf";   // character array — modifiable, on stack
```

> `strlen()` for character arrays only. `size()` on char array includes `\0`; `string::size()` does not.  
> String literal is a `const char` array in read-only memory.

**Swapping two numbers (no temp variable):**

![](cpp_notes_images/56_swap_numbers_xor.png)

---

## ⚙️ Functions

### Returning by Reference

Compilers can return references instead of values (avoids copies):

![](cpp_notes_images/57_function_overload_examples.png)

---

### Function Overloading

Multiple functions with the same name but different parameter lists in the same scope.

![](cpp_notes_images/58_function_overload_int_double.png)

**Allowed:**

![](cpp_notes_images/59_function_overload_allowed1.png)

![](cpp_notes_images/60_function_overload_allowed2.png)

![](cpp_notes_images/61_function_overload_allowed3.png)

**Not allowed:**

![](cpp_notes_images/62_function_overload_not_allowed1.png)

![](cpp_notes_images/63_function_overload_not_allowed2.png)

When `int` is passed → int overload called; `double` → double overload called:

![](cpp_notes_images/64_when_overload_called.png)

---

### Lambda Functions

![](cpp_notes_images/65_lambda_syntax.png)

![](cpp_notes_images/66_lambda_example_full.png)

Use `;` after function body — lambda is a **statement**. Return type is optional (compiler deduces it).

![](cpp_notes_images/67_lambda_with_return.png)

If lambda returns something it assigns to the variable `fun`.

**Capture Lists:**

![](cpp_notes_images/68_lambda_capture_intro.png)

Capture by value makes a **copy** — later changes to the variable won't affect the lambda:

![](cpp_notes_images/69_lambda_capture_variable.png)

![](cpp_notes_images/70_lambda_capture_by_value.png)

![](cpp_notes_images/71_lambda_capture_value_copy.png)

Using variable as reference:

![](cpp_notes_images/72_lambda_capture_by_reference.png)

![](cpp_notes_images/73_lambda_reference_address.png)

> `[=]` captures all surrounding variables by value. `[&]` captures all by reference. With reference, all share the same address.

---

### Function Templates

A **blueprint** — compiler generates actual code when the function is called.

![](cpp_notes_images/74_function_template_intro.png)

`T` is a placeholder for the data type. All arguments must be same type (unless explicitly set).

![](cpp_notes_images/75_function_template_blueprint.png)

![](cpp_notes_images/76_function_template_code.png)

Explicitly set the type to handle different argument types:

![](cpp_notes_images/77_function_template_explicit_type.png)

> View internal template code generation at [cppinsights.io](https://cppinsights.io)

**Template by reference:**

![](cpp_notes_images/78_template_by_reference.png)

> Calling `maximum(a,b)` with both value and reference templates causes confusion:

![](cpp_notes_images/79_template_overload_confusion.png)

---

### Template Specialization

For `const char*` — regular comparison (`>`) doesn't work. Use `strcmp`:

![](cpp_notes_images/80_template_specialization_const_char.png)

Must declare **primary template** first:

![](cpp_notes_images/81_template_specialization_primary.png)

![](cpp_notes_images/82_template_specialization_in_order.png)

Full code:

![](cpp_notes_images/83_template_specialization_code1.png)

![](cpp_notes_images/84_template_specialization_code2.png)

> See [`strcmp` on cppreference](https://en.cppreference.com/w/cpp/string/byte/strcmp)

---

## 🧩 C++20 Concepts & Type Traits

### Concepts

A **concept** constrains template parameters — compile-time enforcement.

![](cpp_notes_images/85_concept_integral_example.png)

Compile with `-std=c++20`:

![](cpp_notes_images/86_concept_std_c20_compile.png)

Before C++20 — use `static_assert` with a custom message:

![](cpp_notes_images/87_concept_before_c20_static_assert.png)

---

### Type Traits (C++11)

Small template tools that query or transform types at **compile time**.

Using type traits with `requires`:

![](cpp_notes_images/88_type_traits_requires_example.png)

![](cpp_notes_images/89_type_traits_in_requires.png)

**Some type traits:**

![](cpp_notes_images/90_some_type_traits.png)

**Ways to declare concepts:**

![](cpp_notes_images/91_concept_declaration_ways1.png)

![](cpp_notes_images/92_concept_declaration_ways2.png)

Syntax 3 — only with `auto`:

![](cpp_notes_images/93_concept_syntax3_auto.png)

![](cpp_notes_images/94_concept_syntax3_auto_example.png)

**Type trait example — `if constexpr`:**

![](cpp_notes_images/95_type_traits_example_full.png)

`if constexpr` — compiler selects branch at **compile time** and discards the other:

![](cpp_notes_images/96_constexpr_if_branch_selection.png)

Compare with/without `constexpr` on [cppinsights.io](https://cppinsights.io):

![](cpp_notes_images/97_constexpr_cppinsights_with.png)

![](cpp_notes_images/98_constexpr_cppinsights_without.png)

---

### Custom Concepts

**Example 1 — integral only:**

![](cpp_notes_images/99_custom_concept_example1.png)

Line 9-10: custom concept. Line 13: function checks parameter satisfies concept — float/double gives compiler error.

**Different ways to use concepts:**

![](cpp_notes_images/100_custom_concept_diff_ways1.png)

![](cpp_notes_images/101_custom_concept_diff_ways2.png)

![](cpp_notes_images/102_custom_concept_diff_ways3.png)

![](cpp_notes_images/103_custom_concept_diff_ways4.png)

**Example 2 — Multipliable:**

![](cpp_notes_images/104_custom_concept_example2_multipliable.png)

Line 10-11: requires two parameters that are multipliable. Passing `char` → concepts not satisfied → error.

**Example 3 — different types (`a` = int, `b` = double):**

![](cpp_notes_images/105_custom_concept_example3_two_types.png)

---

### Deep Dive into `requires`

`requires { ... }` checks whether an **expression is valid (well-formed)** — NOT whether its value is true/false.

![](cpp_notes_images/106_requires_deep_dive_simple.png)

`sizeof(T) <= 4` is always syntactically valid — passes even when T is 8 bytes:

![](cpp_notes_images/107_requires_sizeof_always_valid.png)

![](cpp_notes_images/108_requires_sizeof_invalid_check.png)

Correct way — use `requires sizeof(T) <= 4` (nested requirement):

![](cpp_notes_images/109_requires_sizeof_correct_way.png)

Or use nested requirement directly:

![](cpp_notes_images/110_requires_nested_requirement.png)

**Using logical operators:**

![](cpp_notes_images/111_requires_logical_operator.png)

![](cpp_notes_images/112_requires_example_double_star.png)

---

### `exit()`

![](cpp_notes_images/113_exit_function_example.png)

![](cpp_notes_images/114_exit_code_example.png)

![](cpp_notes_images/115_exit_codes_explanation.png)

> `exit(0)` = success. `exit(1)` = error/abnormal termination. **Terminates the entire program**, even from inside a function.

> ⚠️ Passing an array to a function passes its reference through pointer — not a copy.

---

## 🏛️ OOP — Object-Oriented Programming

### Classes & Objects

**Class** = blueprint. **Object** = real instance of the class.

![](cpp_notes_images/116_class_blueprint_example.png)

- `public` — accessible outside the class
- `private` — only accessible inside the class (**default if not specified**)
- `protected` — access specifier for inheritance
- Member variables should be **private**

![](cpp_notes_images/117_class_private_members.png)

---

### Constructors

![](cpp_notes_images/118_constructor_types.png)

1. **Default constructor** — no parameters
2. **Parameterized constructor** — has parameters

![](cpp_notes_images/119_constructor_parameterized.png)

If compiler sees any constructor, it won't auto-generate a default one.

Two ways to declare default constructor:

![](cpp_notes_images/120_constructor_default_declaration.png)

---

### Setters & Getters

Private members are not accessible from outside. Setters/getters are methods to modify or read member variables of a class.

---

### `#ifndef` Include Guard

![](cpp_notes_images/121_ifndef_include_guard.png)

Prevents redefinition errors when same header is included in multiple files.

---

### Scope Resolution Operator `::`

Used when a class function is defined in another file:

![](cpp_notes_images/122_scope_resolution_operator.png)

Function prototype must be declared inside the class.

---

### Managing Objects with Pointers

![](cpp_notes_images/123_pointer_object_management.png)

`->` is the dereferencing operator. Works like `(*c2).findcir()`.

Pointer (`c2`) lives on stack; object lives on **heap**. Direct object creation → stack. Pointer creation (`new`) → heap.

![](cpp_notes_images/124_pointer_vs_stack_object.png)

> Always release heap memory. Reset pointer to `nullptr` after `delete`.

---

### Destructors

Destructors are called by the compiler to destroy objects:

![](cpp_notes_images/125_destructor_declaration.png)

**When is destructor called?**

![](cpp_notes_images/126_destructor_when_called.png)

- When local stack object goes out of scope
- When heap object is released with `delete`
- No parameters. Not auto-called for heap data.

If 3 objects (d1, d2, d3) — destructor called in **reverse order** (d3 first, d1 last):

![](cpp_notes_images/127_destructor_order_explained.png)

![](cpp_notes_images/128_destructor_d1_stack.png)

**`string_view` in destructors:**

![](cpp_notes_images/129_string_view_in_destructor.png)

![](cpp_notes_images/130_string_view_code.png)

**`string_view` vs `string`:**

![](cpp_notes_images/131_string_view_vs_string.png)

![](cpp_notes_images/132_string_view_vs_string_code1.png)

![](cpp_notes_images/133_string_view_vs_string_code2.png)

---

### `this` Pointer

`this` is a special pointer maintained by C++ — contains the **address of the current object**.

![](cpp_notes_images/134_this_pointer_intro.png)

![](cpp_notes_images/135_this_pointer_print_address.png)

**Chained call using pointer:**

![](cpp_notes_images/136_chained_call_pointer.png)

**Chained call using reference** (`const` is important):

![](cpp_notes_images/137_chained_call_reference.png)

What happens at line 33:

![](cpp_notes_images/138_chained_call_line33.png)

---

### Struct vs Class

![](cpp_notes_images/139_struct_vs_class_differences.png)

![](cpp_notes_images/140_struct_vs_class_table.png)

- `struct` — members **public** by default
- `class` — members **private** by default
- Both are almost the same. Use `struct` for simple public data groups.

---

### Object Size & Memory Alignment

Object size depends on **member variables** — not functions.

![](cpp_notes_images/141_class_object_size_string.png)

`string` size = 32 bytes always (internal pointers + metadata). Characters stored in separate heap allocation:

![](cpp_notes_images/142_string_dynamic_heap_storage.png)

For small strings there may be different scenarios (SSO — Small String Optimization):

![](cpp_notes_images/143_string_sso_small_string.png)

![](cpp_notes_images/144_string_size_explanation.png)

**Object size example:**

![](cpp_notes_images/145_object_size_example.png)

Expected: 44 bytes. Actual: **48 bytes** — alignment rule:

![](cpp_notes_images/146_object_alignment_rule.png)

Total object size must be a multiple of the **largest alignment** (here: 8 bytes for `double`). 4-byte padding added after `int`.

Memory layout:

![](cpp_notes_images/147_object_padding_layout.png)

> **Offset** = byte position of a member from the object start.

Functions don't contribute to object size:

![](cpp_notes_images/148_functions_no_size_contribution.png)

---

## 🧬 Inheritance

Inheritance lets a **derived class** inherit properties and behaviours from a **base class**.

![](cpp_notes_images/149_inheritance_example.png)

`public`, `private`, `protected` access specifiers:

![](cpp_notes_images/150_inheritance_access_specifiers.png)

Player inherits all public members of Human but can't access private ones. Must use setters/getters for private members.

**Protected members** — accessible in derived class but not outside:

![](cpp_notes_images/151_inheritance_protected_member.png)

**Base class access specifier** (`public` inheritance):

![](cpp_notes_images/152_inheritance_base_access_specifier.png)

Accessibility table:

![](cpp_notes_images/153_inheritance_accessibility_table.png)

**Public Inheritance rules:**

![](cpp_notes_images/154_inheritance_public_rules.png)

1. `public` in base → remains `public` in derived
2. `protected` in base → remains `protected` in derived
3. `private` → never inherited

Other inheritance types:

![](cpp_notes_images/155_inheritance_private_protected.png)

![](cpp_notes_images/156_inheritance_access_summary.png)

---

## 📚 Useful References

| Resource | Link |
|----------|------|
| cppreference — Manipulators | https://en.cppreference.com/w/cpp/io/manip |
| cppreference — Numeric Limits | https://en.cppreference.com/w/cpp/types/numeric_limits |
| cppreference — `<cmath>` | https://en.cppreference.com/w/cpp/header/cmath |
| IEEE 754 Explained | https://www.youtube.com/watch?v=8afbTaA-gOQ&t=181s |
| Exception Handling (Anisul Islam) | https://www.youtube.com/watch?v=uoCuMTzD9AE |
| strcmp — cppreference | https://en.cppreference.com/w/cpp/string/byte/strcmp |
| C++ Insights (template codegen) | https://cppinsights.io |
| cppreference.com | https://www.cppreference.com |

---

<div align="center">

Made with ❤️ by **Emon** — SUST

</div>
