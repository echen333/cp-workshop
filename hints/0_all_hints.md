
# A

To read in input, use cin.

For example, read in two integers as:

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    // Input is "5 3"
    int a,b;
    // a = 5, b = 3
    cin >> a >> b;
}
```

You will need a read the number of test cases and write a for loop in addition.

# B

If we have a really large $n$, we should give 1's. If we gave 1 last time, we should give 2.
# C

imagine the case for 4,8,12
now imagine the case for 2 vs. 6

# D

If its not sorted, we know the answer is just 0. Now we can say the array must be sorted and a non-decreasing array.

To make $a$ not sorted, we just need to pick one index $i$ so $a_i>a_{i+1}$. How do we do this?
# E

Do the sample test cases provide any hints?

Think about how you would compute $1+2+3+...+n$ and why it equals $n*(n+1)/2$?

# F
For n=7 or 9, what pair is best?

# G

What is the simplest case for this problem?
# H
Does it even matter the position of the elements in the string. as in can we solve the problem by just knowing the number of 0's and 1's?

# I
Notice we just need 3 of the 4 numbers to be almost prime. We can just let the fourth number be our "filler" for our three fixed numbers.

Sometimes, all four may not be all distinct, but we can handle that case in the end.

# J
What is the tightest bound possible? What if can set one of the numbers to l.

# K
you need to use a long long here to hold numbers up to $10^{18}$.

there should always be an answer if we can find an integer x such that $2^x \cdot a = b$

# L
first look at if there was no $|x-y|=1$ condition
# M
if y is cheaper than twice of x, what can you say about when to use a 1x2 block?

# N
What's the greediest solution? Give all you can to 1 player and spread evenly over rest.

# O
If $b$ is cheap, theoretically, we would like to decrease $x$ and $y$ at the same time. At what $b$ would it be more efficient to just use 2 $a$'s?

Make sure to use long long's since the total cost might be over 2e9.

# P
Consider using a hashmap to keep track of frequencies for each number. Alternatively, sort the numbers to count the largest frequency.

# Q
Think about how to calculate average of $n$ numbers.

# R

Notice the condition in order to add of $a_i$, $i$ must be less than $j$, so try starting from the end to the beginning of the array.

# S

Are there any easy solutions after you sort the array?

# T

Can you do it with the greedy  approach?

# U

Suppose the answer was interval [l,r]. Let's fix $r$ to find the largest $l$<$r$ that works.

To speed this up, is there a way we can use the answer from $r-1$ to find the answer for $r$?

# V

Think of simple solutions that generalize to all sudoku boards.

# W
The trickier things to calculate is the number of partitions with this value. How can you calculate it given that each of the $k$ largest numbers must be in their own partition?

Also remember to use long long's here.

# X
What can you say about the parity of the number of 1's for a successful string?

# Y

Say you only started with 2 colors and try your best to win. How would you go about it?

Make sure you flush your output!

# Z

What can you say about the differences between pairs of $X_i$ and your ability to make numbers?

