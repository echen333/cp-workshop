# I: Captain Flint and Crew Recruiting

![](../img/I.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

void solve() {
    int n;
    cin >> n;
    if (n >= 31) {
        cout << "YES" << '\n';
        int x = n - 30;
        if (x==6 || x==10 || x==14) {
            cout << "15 10 6 " << x-1 << '\n';
        } else {
            cout << "14 10 6 " << x << '\n';
        }
    } else {
        cout << "NO" << '\n';
    }
}

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```