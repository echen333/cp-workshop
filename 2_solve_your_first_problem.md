# Solve your first problem

*Prev: [Setup](./1_setup.md)*

## Introduction to C++

For most help, search on Google. Reading docs might be helpful, but they go into a lot more detail than you would need now.

### Basics and Program Structure

In C++, the entry point of the program is the `main` function. Here's a simple example:

```cpp
#include <iostream>

int main() {
  std::cout << "Hello, world!" << '\n';
  return 0;
}
```

### Primitives

C++ has several basic data types, including:

- Integer (`int`): e.g., `int x = 42;`
- Floating-point (`float`, `double`): e.g., `float y = 3.14;`
- Character (`char`): e.g., `char letter = 'A';`
- Boolean (`bool`): e.g., `bool isTrue = true;`

See that we create variables by specificying the type and then the variable name:

### Strings

Strings in C++ can be handled using the std::string class:

```cpp
#include <string>

std::string name = "John";
```

### Arrays

Arrays are a fixed-size collection of elements of the same type:

```cpp
int numbers[5] = {10, 20, 30, 40, 50};
```

Here is how to initialize an array of a fixed size. Note you need to let the compiler know that the size N is constant if you are initializing a global array (global meaning outside `main()`, global is recommended).
```cpp
const int N=1e3;

int numbers[N]
```

### Loops

For loops in C++ have a similar structure to other languages:

```cpp
for(int i = 0; i < 10; i++) {
// by adding `using namespace std`, we can just use 'cout'
  std::cout << i << '\n';
}
```

While loops continue as long as a condition is true:

```cpp
int i = 0;
while(i < 10) {
  std::cout << i << '\n';
  i++;
}
```

## Go to our codeforces mashup

1. Go to [`codeforces.com`](codeforces.com) -> `Groups` in the headings bar -> `Gatech ICPC`.
   1. If you don't see Gatech ICPC, refer back to `README.md`
   2. This is where practice problemsets and competitions are held.
2. You should see `Beginner Workshop`. Press enter.
   1. We have compiled a set of 26 problems for y'all.
   2. From now until the end of the workshop, try solving as many as you can. This is one of the only measurements you should judge your progress for this workshop by.
   3. The top $x<10$ (*undisclosed*) people that solve the most problems will get a special prize.
   4. We are here to help you! Let us know of any ideas you've thought about.

## The first problem, A+B

The problem statement requires us to read in two integers and print out their sum. See if you can figure it out.

A hint is provided [here](./hints/A.md).

To submit your solution, submit by pasting your code under `Submit Code` in the top panel or by choosing your `.cpp` file on right-side panel.

Codeforces will then redirect you to your `Status` page. Your status will be one of the following:

- AC (Accepted): Congratulations! Solution passed all tests.
- WA (Wrong Answer): Solution produced incorrect output for test case $x$.
- TLE (Time Limit Exceeded): Solution took too long to run. Check for infinite loops or your time complexity (covered later).
- MLE (Memory Limit Exceeded): Solution used too much memory.
- RTE (Runtime Error): Solution failed while running (e.g., division by zero or array out of bounds).
- Compile Error: Failed to Compile

Let us know if you need help debugging!

## What's next

Now, [what's next?](./3_practice_practice_practice.md)
