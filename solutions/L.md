# L: Similar Pairs

![](../img/L.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MX = 50;

int arr[MX];

void solve() {
    int n;
    cin >> n;
    int num_evens = 0;
    for (int i=0;i<n;i++) {
        cin >> arr[i];
        if (arr[i]%2==0) {
            num_evens++;
        }
    }
    if (num_evens%2 == 0) {
        // just pair all the evens together and all the odds together
        cout << "YES" << '\n';
    } else {
        //otherwise it depends on whether we have >=1 pair where |x-y|=1
        sort(arr,arr+n);
        bool flag = false;
        for (int i=1;i<n;i++) {
            if (arr[i] - arr[i-1] == 1) {
                flag = true;
            }
        }
        if (flag) {
            cout << "YES" << '\n';
        } else {
            cout << "NO" << '\n';
        }

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