# M: New Theatre Square

```cpp
#include "bits/stdc++.h"

using namespace std;

const int MX = 101;
const int MX2 = 1001;

bool done[MX][MX2];

void solve() {
    int n,m,x,y;
    cin >> n >> m >> x >> y;
    y = min(2*x, y);
    int cost = 0;
    for (int i=0;i<n;i++) {
        string S; cin >> S;
        for (int j=0;j<m;j++) {
            if (done[i][j] || S[j] == '*') {
                continue;
            }
            if (j!=m-1 && S[j+1]=='.') {
                //try to use a 1x2 block
                done[i][j] = true;
                done[i][j+1] = true;
                cost += y;
                continue;
            }
            cost += x;
        }
    }
    cout << cost << endl;

    for (int i=0;i<n;i++) {
        for (int j=0;j<m;j++) {
            //clear done's for next test case
            done[i][j] = false;
        }
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