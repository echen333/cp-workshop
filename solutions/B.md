# B: Little Artem and Presents

We need to make sequence of moves like: 1, 2, 1, 2, ...

So the answer is 2 * n / 3. After that we have either 0, 1 or 2 stones left. If we have 0, we are done, otherwise we have 1 or 2 left, so we only can give 1 more stone.

Final formula is: (2 * n) / 3 + (n % 3 != 0 ? 1 : 0);

```cpp
#include "bits/stdc++.h"

using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    int n;
    cin >> n;
    int ans = n/3*2 + (n%3>0);
    cout << ans << '\n';
}
```