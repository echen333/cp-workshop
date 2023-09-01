```cpp
#include "bits/stdc++.h"

using namespace std;

const int MXN = 9;

int arr[MXN][MXN];

void solve() {
    for (int i=0;i<9;i++) {
        string S;
        cin >> S;
        for (int j=0;j<9;j++) {
            // cute trick to turn characters into ints
            arr[i][j] = S[j] - '0';
        }
    }
    for (int i=0;i<3;i++) {
        for (int j=0;j<3;j++) {
            int &x = arr[3*i+j][3*j+i];
            // see https://cplusplus.com/doc/tutorial/pointers/
            if (x == 1){
                x = 2;
            } else {
                x = 1;
            }

        }
    }

    for (int i=0;i<9;i++) {
        for (int j=0;j<9;j++) {
            cout << arr[i][j];
        }
        cout << '\n';
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