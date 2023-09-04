
# C: Watermelon

We can always split the watermelon if $n$ is an even integer $>=4$.

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    int n;
    cin >> n;
    if (n%4==0 || (n%2==0 && n>=6)) {
        cout << "YES" << '\n';
    } else {
        cout << "NO" << '\n';
    }
}
```