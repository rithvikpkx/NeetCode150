# Valid Anagram — NeetCode 150 #2

Given two strings `s` and `t`, return true if the two strings are anagrams of each other, otherwise return false.

An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different.

## Examples

*Example 1:*

Input: s = "racecar", t = "carrace"

Output: true


*Example 2:*

Input: s = "jar", t = "jam"

Output: false


## Thought Process

- The premise is to determine if two passed-in strings are anagrams or not
- We need some way to compare them — bring both strings to a consistent state and compare
- That consistent state is sorted order: if the two sorted strings match, they are anagrams; if not, they aren't

## My Solution

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        // Quick check: if string lengths don't match then they can't be anagrams
        if (s.length() != t.length()) {
            return false;
        }

        char[] s_letters = s.toCharArray();
        char[] t_letters = t.toCharArray();

        Arrays.sort(s_letters);
        Arrays.sort(t_letters);

        return (Arrays.equals(s_letters, t_letters));
    }
}
```

## Explanation

- First, check if the two strings have different lengths — if so, they cannot be anagrams, so return false immediately

- Convert both strings to character arrays so they can be sorted

- Sort both character arrays — this brings them to a canonical order where characters appear in the same sequence regardless of their original order

- Compare the two sorted arrays: if they are equal, the strings contain the same characters and are anagrams; otherwise they are not
