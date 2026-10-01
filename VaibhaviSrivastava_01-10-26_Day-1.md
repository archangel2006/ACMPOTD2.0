# 14A. Letter

## Beginner: 800

### Brief Description

Find the minimum bounding rectangle that contains all the shaded (`*`) cells.  
Track the minimum and maximum row and column containing `*`, then print all cells within those boundaries.

### Solution

```bash

#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, m;
    cin >> n >> m;

    vector<string> a(n);

    // input the grid
    for (int i = 0; i < n; i++)
        cin >> a[i];

    // boundaries of the rectangle containing all '*'
    int min_r = n, max_r = -1;
    int min_c = m, max_c = -1;

    // Find min and max row/column containing '*'
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (a[i][j] == '*') {
                min_r = min(min_r, i);
                max_r = max(max_r, i);
                min_c = min(min_c, j);
                max_c = max(max_c, j);
            }
        }
    }

    // Print the bounding rectangle
    for (int i = min_r; i <= max_r; i++) {
        for (int j = min_c; j <= max_c; j++) {
            cout << a[i][j];
        }
        cout << '\n';
    }

    return 0;
}

```

### Accepted Solution

<img width="1838" height="61" alt="image" src="https://github.com/user-attachments/assets/93f30789-9b95-445c-a819-6ede718b7061" />

