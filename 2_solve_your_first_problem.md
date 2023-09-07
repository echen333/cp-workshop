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

*Note*: you may see `std::cout`, which is referencing the `cout` object in the `std` library (library also includes utilities like `sort`, `string`, and `vector`). We can truncate the `std::` by writing `using namespace std` at the beginning of our program to let our compiler know we want everything in the `std` namespace.

### Primitives

C++ has several basic data types, including:

- Integer (`int`): e.g., `int x = 42;`
- Floating-point (`float`, `double`): e.g., `float y = 3.14;`
- Character (`char`): e.g., `char letter = 'A';`
- Boolean (`bool`): e.g., `bool isTrue = true;`

See that we create variables by specificying the type and then the variable name:

### Strings

Strings in C++ can be handled using the std::string class. They are represented internally as an array of `char`'s.

```cpp
string name = "John";
cout << name[1]; \\o
cout << name.substr(2,2); \\hn
```

### Arrays

Arrays are a fixed-size collection of elements of the same type:

```cpp
int numbers[5] = {40, 10, 20, 50, 30};
cout << numbers[1]; // 10
sort(numbers, numbers+5);
reverse(numbers, numbers+5);
cout << numbers[0]; // 50
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

## Go to our codeforces mashup

1. Go to [`codeforces.com`](https://codeforces.com) -> `Groups` in the headings bar -> `Gatech ICPC`.
   1. If you don't see Gatech ICPC, refer back to `README.md`
   2. This is where practice problemsets and competitions are held.
2. You should see [`Beginner Workshop`](https://codeforces.com/group/j7YsoIFtw4/contest/470347). Press enter.
   1. We have compiled a set of 26 problems for y'all.
   2. From now until the end of the workshop, try solving as many as you can. This is one of the only measurements you should judge your progress for this workshop by.
   3. The top $x<10$ (*undisclosed*) people that solve the most problems will get a special prize.
   4. We are here to help you! Let us know of any ideas you've thought about.

## Reading in input in C++

In C++, cin with the extraction operator >> reads input until it encounters a whitespace (space, tab, newline). This makes it convenient for space-separated input.

**Space-separated input:**

```cpp
// Reading integers
int a, b;
cin >> a >> b;  // Input: 10 20

// Reading strings (single words)
string word;
cin >> word;  // Input: Hello

// Can also read in char's or double or other primitives
char c;
cin >> c;
```

## The first problem, A+B

The problem statement requires us to read in two integers and print out their sum.

Let's start out with our template code provided [here](./appendix/template.cpp).

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    // magic lines to make i/o faster, refer to https://stackoverflow.com/a/31165481 if you're curious why
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    cout << "Hello World" << '\n';
}
```

We first have to read in $t$, the number of test cases in the input. We will then have to loop $t$ times, reading in two integers each time.

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    // magic lines to make i/o faster, refer to https://stackoverflow.com/a/31165481 if you're curious why
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
      int a,b;
      cin >> a >> b;
      cout << a+b << endl;
    }
}
```

There we go! Try running it locally, copying the input from Codeforces and pasting it inside your Terminal. Your output should match the output on Codeforces.

Now, try submitting! To submit your solution, submit by pasting your code under `Submit Code` in the top panel or by choosing your `.cpp` file on right-side panel. **Select your language as `GNU G++20 11.2.0`.**

Codeforces will then redirect you to your `Status` page. Your will get one of the following statuses:

- AC (**Accepted**): Congratulations! Solution passed all tests.
- WA (**Wrong Answer**): Solution produced incorrect output for test case $x$.
- TLE (**Time Limit Exceeded**): Solution took too long to run. Check for infinite loops or your time complexity (covered later).
- MLE (**Memory Limit Exceeded**): Solution used too much memory.
- RTE (**Runtime Error**): Solution failed while running (e.g., division by zero or array out of bounds).
- **Compile Error**: Failed to Compile

Let us know if you need help debugging!

## What's next

Now, [**what's next?**](./3_practice_practice_practice.md)
