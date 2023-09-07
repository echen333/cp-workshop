# A

To read in input, use cin.

For example, read in two integers as:

```cpp
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
```

You will need a read the number of test cases and write a for loop in addition.
