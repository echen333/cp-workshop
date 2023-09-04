# W: Permutation Partitions

![](../img/W.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 2e5+5;
const int MOD = 998244353;

int arr[MXN];

void solve() {
    int n,k;
    cin >> n >> k;
    for (int i=0;i<n;i++) {
        cin >> arr[i];
    }
    long long ways = 1;
    long long sum = 0;
    for (int i=n-k+1;i<=n;i++) {
        sum += i;
    }
    vector<int> v;
    for (int i=0;i<n;i++) {
        if (arr[i] >= n-k+1) {
            //this must be in its own partition
            v.push_back(i);
        }
    }
    for (int i=1;i<v.size();i++) {
        ways = ways * (v[i]-v[i-1]) % MOD;
    }
    cout << sum << " " << ways << '\n';
}

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    int t=1;
    // cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```