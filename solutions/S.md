# S: Sorted Adjance Differences

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 1e5 + 5;

int arr[MXN];
int ans[MXN];

void solve() {
    int n; cin>>n;
    for (int i=0;i<n;i++) {
        cin >> arr[i];
    }
    sort(arr,arr+n);

    int l=0, r=n-1; // start from the two ends of the arr
    for (int i=0;i<n;i++) {
        if (i%2==0) {
            ans[i] = arr[l];
            l++;
        } else {
            ans[i] = arr[r];
            r--;
        }
    }
    // after reversing, the answer starts from the middle and bounces out
    reverse(ans, ans+n);
    for (int i=0;i<n;i++) {
        cout << ans[i] << " ";
    }
    cout << endl;
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```