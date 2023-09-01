# U: Ternary String

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 2e5 + 5;

int arr[MXN];

void solve() {
    string S;
    cin >> S;
    int lst_1=-1, lst_2=-1, lst_3=-1;
    int ans = 1e9;
    for (int i=0;i<S.size();i++) {
        int fst = -1;
        if (S[i]=='1') {
            lst_1 = i;
            fst = min(lst_2,lst_3);
        }
        if (S[i]=='2') {
            lst_2 = i;
            fst = min(lst_1,lst_3);
        }
        if (S[i]=='3') {
            lst_3 = i;
            fst = min(lst_1,lst_2);
        }
        if (fst == -1)
            continue;
        ans = min(ans, i-fst+1);
    }
    cout << (ans == 1e9?0:ans) << endl;

}

int main() {
    int t;
    cin >> t;
    for (int i=0;i<t;i++) {
        solve();
    }
}
```