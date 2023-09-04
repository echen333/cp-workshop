# P: Two Teams Composing

![](../img/P.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

void solve() {
    int n; cin >> n;
    map<int,int> m;
    for (int i=0;i<n;i++) {
        int x;cin>>x;
        m[x]++;
    }
    int ans = 1;
    for (pair<int,int> x: m) {
        ans = max(ans, x.second);
    }

    int distinct_nums = m.size();
    if (distinct_nums-1 >= ans) {
        cout << ans << '\n';
    } else {
        cout << min(ans-1, distinct_nums) << '\n';
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