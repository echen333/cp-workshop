# N: Berland Poker

![](../img/N.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

void solve() {
    int n,m,k;
    cin >> n >> m >> k;
    int hand_size = n/k;
    int my_jokers = min(m, hand_size);
    int rest_jokers = m - my_jokers;
    // divide evenly over rest of k-1 players
    // ceil division of a/b is (a+b-1)/b
    int rest_most = (rest_jokers+k-2)/(k-1);
    cout << my_jokers - rest_most << endl;
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```