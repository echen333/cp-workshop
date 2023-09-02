# C++ Standard Library

Read through the beginning of [Chapter 4](https://cses.fi/book/book.pdf#page=45) of the CSES handbook on data structures. 

I don't think any of the problems in the problemset requires data structures beyond sets, vectors, and maps (and very few do require these).

Some notes:

- a `vector` in C++ is analagous to `ArrayLists` in Java.

## An example

**Problem**: Suppose we are given an array $a_1,a_2,.., a_n$. Count how many distinct numbers are in the array.

**Solution 1**: First sort the array. Then loop through the array, incrementing count by one if the previous number was different.

**Solution 2**: Insert $a_1,a_2,...,a_n$ into a `set<int>`. The property that elements in a set are all distinct means the answer is just `my_set.size()`.

## Next Steps

If you got this far, you should have all the prerequisite person knowledge to solve all remaining 21 problems in the set. This will take a lot of time, but perseverance is required.

Remember, we are here to help if you have questions. But we also strongly encourage you to solve problems on your own time aside from workshop times and report back to us with any questions. We specifically made sure the problem difficulty curve was as small as possible.

From now until the end of the workshop, try solving as many as you can. The top $x<10$ (*undisclosed*) people that solve the most problems will get a special prize.
