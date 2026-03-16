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



Problem 2: Sort by Set Bits Count
Description:
You are given an array of integers. Your task is to implement a sorting algorithm that arranges the numbers in the array based on following conditions and return that array:

Numbers with an even count of set bits should appear first in ascending order.
Following that, numbers with an odd count of set bits should be arranged in ascending order.


Input Format:

The first line contains T denoting the number of test cases.
For each test case:

The first line contains the integer N.
The second line contains the array of length N.



Output Format:

For each test case, print the answer in a new line.


Sample Input:
1
6
5 2 8 12 7 6
Sample Output:
5 6 12 2 7 8
Explanation:

Binary representations:

5 = 101 → 2 set bits (even) ✓
2 = 10 → 1 set bit (odd)
8 = 1000 → 1 set bit (odd)
12 = 1100 → 2 set bits (even) ✓
7 = 111 → 3 set bits (odd)
6 = 110 → 2 set bits (even) ✓


Even set bits (ascending): 5, 6, 12
Odd set bits (ascending): 2, 7, 8
Final output: 5 6 12 2 7 8


Solution
javaimport java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.*;

class TestClass {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        
        while(t-- > 0) {
            int n = sc.nextInt();
            Integer arr[] = new Integer[n];
            
            for(int i = 0; i < n; i++) {
                arr[i] = sc.nextInt();
            }
            
            Arrays.sort(arr, (a, b) -> {
                int countA = Integer.bitCount(a);
                int countB = Integer.bitCount(b);
                
                // If one has even set bits and other has odd
                if(countA % 2 != countB % 2) {
                    return (countA % 2) - (countB % 2);
                }
                
                // Both have same parity, sort in ascending order
                return a - b;
            });
            
            for(int x : arr) {
                System.out.print(x + " ");
            }
            
            System.out.println();
        }
    }
}

Time Complexity: O(N log N)
Space Complexity: O(N)Share(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.nonce='xLbRkE0MGs1iAVsXvBUwzQ==';d.innerHTML="window.__CF$cv$params={r:'9dd48e0fca927fab',t:'MTc3MzY3MjQ2NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='xLbRkE0MGs1iAVsXvBUwzQ==';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();
