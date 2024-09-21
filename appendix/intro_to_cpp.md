# Introduction to C++

For most help, search on Google. Reading docs might be helpful, but they go into a lot more detail than you would need now. ChatGPT is also a very helpful tool you can use (outside of competitions!) that helps display the part of the docs *you actually need* in a concise format.

## Basics and Program Structure

In C++, the entry point of the program is the `main` function. Here's a simple example:

```cpp
#include <iostream>

int main() {
  std::cout << "Hello, world!" << '\n';
  return 0;
}
```

*Note*: you may see `std::cout`, which is referencing the `cout` object in the `std` library (library also includes utilities like `sort`, `string`, and `vector`). We can truncate the `std::` by writing `using namespace std` at the beginning of our program to let our compiler know we want everything in the `std` namespace.

## Primitives

C++ has several basic data types, including:

- Integer (`int`): e.g., `int x = 42;`, defaults to 0
- Floating-point (`float`, `double`): e.g., `float y = 3.14;`
- Character (`char`): e.g., `char letter = 'A';`
- Boolean (`bool`): e.g., `bool isTrue = true;`

See that we create variables by specificying the type and then the variable name:

## Strings

Strings in C++ can be handled using the std::string class. They are represented internally as an array of `char`'s.

```cpp
string name = "John";
cout << name[1]; \\o
cout << name.substr(2,2); \\hn
```

## Arrays

Arrays are a fixed-size collection of elements of the same type:

```cpp
int numbers[5] = {40, 10, 20, 50, 30};
cout << numbers[1]; // 10
sort(numbers, numbers+5);
reverse(numbers, numbers+5);
cout << numbers[0]; // 50
```

Here is how to initialize an array of a fixed size. Note you need to let the compiler know that the size N is constant if you are initializing a global array (global meaning outside `main()`. There are various reasons why fixed size arrays is best declared in the global scope for competitive programming.).

```cpp
const int N=1e3;

int numbers[N]
```

## Loops

For loops in C++ have a similar structure to other languages:

```cpp
for(int i = 0; i < 10; i++) {
// by adding `using namespace std`, we can just use 'cout'
  cout << i << '\n';
}
```

While loops continue as long as a condition is true:

```cpp
int i = 0;
while(i < 10) {
  cout << i << '\n';
  i++;
}
```
