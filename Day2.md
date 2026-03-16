# DAY 2

## Problem 1: Read and Process Input

**Description:**

Read different types of data from standard input, process them as shown in output format and print the answer to standard output.

**Input format:** 
- First line contains integer `N`
- Second line contains string `S`

**Output format:** 
- First line should contain `N × 2`
- Second line should contain the same string `S`

---

**Constraints:**
- `1 ≤ N ≤ 1000`
- `1 ≤ |S| ≤ 100` (where `|S|` is the length of string `S`)

---

**Sample Input:**
```
5
helloworld
```

**Sample Output:**
```
10
helloworld
```

---

### Solution

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.*;

class TestClass {
    public static void main(String args[]) throws Exception {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        s.nextLine();  // Consume the newline character
        String name = s.nextLine();
        
        System.out.println(n * 2);
        System.out.println(name);
    }
}
```

---

**Time Complexity:** O(1)  
**Space Complexity:** O(1)
