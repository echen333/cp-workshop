# R: Kind Anton

![](../img/R.png)

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 1e5 + 5;

int a[MXN], b[MXN];

void solve() {
    int n,x; cin >> n;
    for(int i=0;i<n;i++){
        cin >> a[i];
    }
    for(int i=0;i<n;i++){
        cin >> b[i];
    }
    //find occurence of first +1 and -1
    int first_pos = n, first_neg = n;
    for (int i=n-1;i>=0;i--) {
        if (a[i]==1) {
            first_pos = i;
        }
        if (a[i]==-1) {
            first_neg = i;
        }
    }

    bool works = true;
    for (int i=n-1;i>=0;i--){
        if (a[i]>b[i]) {
            if (first_neg>=i) {
                works = false;
            }
        }
        if (a[i]<b[i]) {
            if (first_pos>=i) {
                works = false;
            }
        }
    }
    cout << (works?"YES":"NO") << endl;
}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```