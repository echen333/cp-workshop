# O: Road to Zero
```cpp
#include "bits/stdc++.h"

using namespace std;

void solve() {
    long long x,y,a,b;
    cin >> x >> y >> a >> b;
    b= min(b,2*a);
    long long cost_decr_both = min(x,y) * b;
    long long cost_decr_larger = abs(x-y) * a;
    cout << cost_decr_both + cost_decr_larger << endl;
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```