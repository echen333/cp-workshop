# B: Little Artem and Presents

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    int n;
    cin >> n;
    int ans = n/3*2 + (n%3>0);
    cout << ans << endl;
}
```