# 📌 Structure

## 📖 What is Structure

- A **structure** is a collection of data members grouped under a single name.
- Data members can be of **same** or **different data types**.
- When a structure is used in the `main()` function, it **consumes memory based on the data members it contains**.
- An example of a structure is representing a **rectangle**.

---

## 💻 Example

```c
#include <stdio.h>

struct Rectangle {
    int length;
    int breadth;
};

int main() {
    struct Rectangle r;                 // Declaration
    struct Rectangle r1 = {10, 5};      // Declaration + Initialization

    r.length = 15;                      // Access using dot (.)
    r.breadth = 10;

    printf("Area of rectangle is %d", r.length * r.breadth); // Accessing members

    return 0;
}
```

## Use of structure

- In Complex numbers
- In student details
- In Employee Details
- Bank Details etc
- Defining Shapes etc

## Padding in structure

```c
#include <iostream>
using namespace std;

struct Rectangle {
    int length;
    int breadth;
    char x;
};

int main() {
    struct Rectangle r1;
    cout<<sizeof(r1)<<endl;
    return 0;
}
```

In this structure, there are two `int` variables and one `char`, so the total size of the actual data is:

`4 + 4 + 1 = 9 bytes`

However, when we use `sizeof`, the structure size becomes **12 bytes** instead of 9.

This happens because of **padding**, which is added by the compiler to satisfy **memory alignment requirements**. Each data type is aligned based on its size (e.g., `int` is usually aligned to 4 bytes).

After storing the `char` (1 byte), the compiler adds **3 extra bytes** so that the total size of the structure becomes a multiple of the largest alignment requirement (4 bytes).

This alignment ensures efficient memory access and proper alignment when creating arrays of structures.

The extra unused bytes added by the compiler are called **padding**.

# Pointer

- Pointer is a address variable that is meant for storing address, not data
  itself
- They are used for indirect access of data
- For a program to use heap memory , pointers is used
- To access heap memory and resources outside the main memory like
  internet, keyboard , monitor etc pointers is used
- Pointers are also used for parameter passing

```c
Int main( )
{
Int a = 10 ; // data variable
Int *p ; // declaration
P = & a ; // Assignment / Initialization
printf( “% d ” , a ) ;
printf(“ %d ” , * p ) ; // dereferencing
}
```

## Accessing Heap memory through pointer

```c
#include<stdio.h>
Int main( )
{
Int * p;
P = new int[5];
}
```
