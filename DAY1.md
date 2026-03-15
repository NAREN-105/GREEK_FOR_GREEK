# DAY 1

## Problem 1: Concatenation of Array

**Description:**

You are given an integer array `nums` of length `n`. Create an array `ans` of length `2n` where `ans[i] == nums[i]` and `ans[i + n] == nums[i]` for `0 <= i < n` (0-indexed).

Specifically, `ans` is the concatenation of two `nums` arrays.

Return the array `ans`.

---

**Example 1:**
```
Input: nums = [1,4,1,2]
Output: [1,4,1,2,1,4,1,2]
```

**Example 2:**
```
Input: nums = [22,21,20,1]
Output: [22,21,20,1,22,21,20,1]
```

---

### Solution

```java
class Solution {
    public int[] getConcatenation(int[] nums) {
        int n = nums.length;
        int k = 0;
        int con[] = new int[nums.length];
        
        for(int i = 0; i < nums.length; i++) {
            con[i] = nums[i];    
        }
        
        int ans[] = new int[n * 2];
        
        for(int i = 0; i < ans.length; i++) {
            if(i < nums.length) {
                ans[i] = nums[i];
            } else {
                ans[i] = con[k];
                k++;
            }
        }
        
        return ans;
    }
}
```

---

**Time Complexity:** O(n)  
**Space Complexity:** O(n)

---

## Problem 2: Score of a String

**Description:**

You are given a string `s`. The score of a string is defined as the sum of the absolute difference between the ASCII values of adjacent characters.

Return the score of `s`.

---

**Example 1:**
```
Input: s = "code"
Output: 24
```
**Explanation:** The ASCII values of the characters in the given string are: `'c' = 99`, `'o' = 111`, `'d' = 100`, and `'e' = 101`. The score of `s` will be: `|111 - 99| + |100 - 111| + |101 - 100|`.

**Example 2:**
```
Input: s = "neetcode"
Output: 65
```

---

### Solution

```java
class Solution {
    public int scoreOfString(String s) {
        int sum = 0;
        char str[] = s.toCharArray();
        
        for(int i = 0; i < str.length - 1; i++) {
            char a = str[i + 1];
            char b = str[i];
            sum += Math.abs((a - 0) - (b - 0));
        }
        
        return sum;
    }
}
```

---

**Time Complexity:** O(n)  
**Space Complexity:** O(n)

---

## Problem 3: Contains Duplicate

**Description:**

Given an integer array `nums`, return `true` if any value appears more than once in the array, otherwise return `false`.

---

**Example 1:**
```
Input: nums = [1, 2, 3, 3]
Output: true
```

**Example 2:**
```
Input: nums = [1, 2, 3, 4]
Output: false
```

---

### Solution

```java
class Solution {
    public boolean hasDuplicate(int[] nums) {
        boolean t = false;
        
        for(int i = 0; i < nums.length; i++) {
            for(int j = i + 1; j < nums.length; j++) {
                if(nums[i] == nums[j]) {
                    t = true;
                }
            }
        }
        
        return t;
    }
}
```

---

**Time Complexity:** O(n²)  
**Space Complexity:** O(1)
