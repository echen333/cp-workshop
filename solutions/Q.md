# Q: Middle Class

![](../img/Q.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 1e5 + 5;

int arr[MXN];

void solve() {
    int n,x; cin >> n >> x;
    for (int i=0;i<n;i++) {
        cin >> arr[i];
    }
    sort(arr,arr+n);
    reverse(arr, arr+n);
    int ans = 0;
    long long sum = 0;
    for (int i=0;i<n;i++) {
        sum += arr[i];
        if (sum >= (long long) x*(i+1)) {
            ans = i+1;
        } else {
            break;
        }
    }
    cout << ans << endl;
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```