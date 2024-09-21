# Solve your first problem

*Prev: [Setup](./2_setup.md)*

If you would like a primer on C++, **please check out our** [introduction to C++](./appendix/intro_to_cpp.md). Otherwise, go ahead and solve your first problem!

## Go to our codeforces mashup

1. Go to [`codeforces.com`](https://codeforces.com) -> `Groups` in the headings bar -> `Gatech ICPC`.
   1. If you don't see Gatech ICPC, refer back to `README.md`
   2. This is where practice problemsets and competitions are held.
2. Use this link to enter the beginner workshop: [`Beginner Workshop`](https://codeforces.com/group/j7YsoIFtw4/contest/551690). You can also scroll down until you find a contest titled "Beginner Workshop".
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

We first have to read in $t$, the number of test cases in the input. We will then have to loop $t$ times, reading in two integers each time. This is our complete code.

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

*Note*: You should always run your code locally before submitting in to Codeforces. There are very few times where you will code bug free, and wrong submissions are penalized during contests. **We should not see any Wrong Answers on Test Case 1!**

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

Now, [**what's next?**](./4_practice_practice_practice.md)
