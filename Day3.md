# DAY 3

## Problem 1: Append Characters to String to Make Subsequence

**Description:**
You are given two strings `s` and `t` consisting of only lowercase English letters. Return the minimum number of characters that need to be appended to the end of `s` so that `t` becomes a subsequence of `s`.

A subsequence is a string that can be derived from another string by deleting some or no characters without changing the order of the remaining characters.

---

**Input Format:**
- A string `s`
- A string `t`

**Output Format:**
- An integer representing the minimum number of characters to append

---

**Constraints:**
- `1 ≤ s.length, t.length ≤ 100,000`
- `s` and `t` consist of only lowercase English letters

---

**Sample Input 1:**
```
s = "coaching", t = "coding"
```
**Sample Output 1:**
```
4
```
**Explanation:**
Append the characters `"ding"` to the end of `s` so that `s = "coachingding"`. Now, `t` is a subsequence of `s` (`coachingding`). It can be shown that appending any `3` characters to the end of `s` will never make `t` a subsequence.

---

**Sample Input 2:**
```
s = "abcde", t = "a"
```
**Sample Output 2:**
```
0
```
**Explanation:**
`t` is already a subsequence of `s` (`"abcde"`).

---

**Sample Input 3:**
```
s = "z", t = "abcde"
```
**Sample Output 3:**
```
5
```
**Explanation:**
Append the characters `"abcde"` to the end of `s` so that `s = "zabcde"`. Now, `t` is a subsequence of `s` (`zabcde`). It can be shown that appending any `4` characters to the end of `s` will never make `t` a subsequence.

---

### Solution

```java
class Solution {
    public int appendCharacters(String s, String t) {
        int i = 0;
        int j = 0;

        while (i < s.length() && j < t.length()) {
            if (s.charAt(i) == t.charAt(j)) {
                j++;
            }
            i++;
        }

        return t.length() - j;
    }
}
```

---

**Time Complexity:** O(N) — single pass through `s`  
**Space Complexity:** O(1) — only two pointers used

---

## Problem 2: Length of Last Word

**Description:**
You are given a string `s` consisting of words and spaces. Return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

---

**Input Format:**
- A string `s` consisting of English letters and spaces

**Output Format:**
- An integer representing the length of the last word

---

**Constraints:**
- `1 ≤ s.length ≤ 10,000`
- `s` consists of only English letters and spaces

---

**Sample Input 1:**
```
s = "Hello World"
```
**Sample Output 1:**
```
5
```
**Explanation:**
The last word is `"World"` with length `5`.

---

**Sample Input 2:**
```
s = "   fly me   to   the moon  "
```
**Sample Output 2:**
```
4
```
**Explanation:**
The last word is `"moon"` with length `4`.

---

**Sample Input 3:**
```
s = "luffy is still joyboy"
```
**Sample Output 3:**
```
6
```
**Explanation:**
The last word is `"joyboy"` with length `6`.

---

### Solution

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int i = s.length() - 1;
        int length = 0;

        // Skip trailing sp
        while (i >= 0 && s.charAt(i) == ' ') {
            i--;
        }
        while (i >= 0 && s.charAt(i) != ' ') {
            length++;
            i--;
        }
        return length;
    }
}
```
---
**Time Complexity:** O(N) — traverses the string from the end  
**Space Complexity:** O(1) — only a pointer and counter used
