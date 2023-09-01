
# C: Watermelon
```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    int n;
    cin >> n;
    if (n%4==0 || (n%2==0 && n>=6)) {
        cout << "YES" << endl;
    } else {
        cout << "NO" << endl;
    }
}
```