# Solve your first problem

## Introduction to C++

### Basics and Program Structure

In C++, the entry point of the program is the `main` function. Here's a simple example:

```cpp
#include <iostream>

int main() {
  std::cout << "Hello, world!" << std::endl;
  return 0;
}
```

### Primitives
C++ has several basic data types, including:

- Integer (`int`): e.g., `int x = 42;`
- Floating-point (`float`, `double`): e.g., `float y = 3.14;`
- Character (`char`): e.g., `char letter = 'A';`
- Boolean (`bool`): e.g., `bool isTrue = true;`

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

### Loops

For loops in C++ have a similar structure to other languages:

```cpp
for(int i = 0; i < 10; i++) {
// by adding `using namespace std`, we can just use 'cout'
  std::cout << i << std::endl;
}
```

While loops continue as long as a condition is true:

```cpp
int i = 0;
while(i < 10) {
  std::cout << i << std::endl;
  i++;
}
```

## Go to our codeforces mashup

ask smax? https://codeforces.com/group/j7YsoIFtw4/contests

## The first problem, Watermelon

Now, [What's next?](./3_practice_practice_practice.md)