```cpp
#include "bits/stdc++.h"

using namespace std;

void solve() {
    int n;
    cin >> n;
    if (n >= 31) {
        cout << "YES" << endl;
        int x = n - 30;
        if (x==6 || x==10 || x==14) {
            cout << "15 10 6 " << x-1 << endl;
        } else {
            cout << "14 10 6 " << x << endl;
        }
    } else {
        cout << "NO" << endl;
    }
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```