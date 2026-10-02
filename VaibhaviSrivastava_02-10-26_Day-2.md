# 16A. Flag

## Beginner: 800

### Brief Description

We iterate through the grid row by row to check two conditions. 
- verify that all characters within the same horizontal row are identical.
- ensure that the color of the current row is different from the color of the row directly above it. 
- If any rule is broken, the flag is invalid.

### Solution

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    int n, m;
    if (!(cin >> n >> m)) return 0;
    
    vector<string> grid(n);
    for (int i = 0; i < n; i++) {
        cin >> grid[i];
    }
    
    bool valid = true;
    for (int i = 0; i < n; i++) {
        // Check if all characters in the current row are identical
        char first_char = grid[i][0];
        for (int j = 1; j < m; j++) {
            if (grid[i][j] != first_char) {
                valid = false;
                break;
            }
        }
        if (!valid) break;
        
        // Check if adjacent horizontal rows have different colors
        if (i > 0 && grid[i][0] == grid[i - 1][0]) {
            valid = false;
            break;
        }
    }
    
    if (valid) {
        cout << "YES\n";
    } else {
        cout << "NO\n";
    }
    
    return 0;
}
```

### Accepted Solution

<img width="[width]" height="[height]" alt="image" src="[GitHub screenshot URL]" />
