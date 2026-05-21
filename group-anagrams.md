# Group Anagrams | Blind 75 #4

Given an array of strings `strs`, group the anagrams together and return the result in any order.

## Examples

**Example 1:**

    Input: strs = ["eat","tea","tan","ate","nat","bat"]
    
    Output: [["bat"],["nat","tan"],["ate","eat","tea"]]


**Example 2:**

    Input: strs = [""]
    
    Output: [[""]]


## Thought Process

- We need some way to bring the words to a consistent form to determine anagrams: sorting
- We also need some way to keep track of the various groups of anagrams: maps

## My Solution

```java
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        HashMap<String, List<String>> anagram_map = new HashMap<>();

        for (String str : strs) {
            char[] letters = str.toCharArray();

            Arrays.sort(letters);

            String sorted_word = new String(letters);

            anagram_map.putIfAbsent(sorted_word, new ArrayList<>());

            anagram_map.get(sorted_word).add(str);
        }

        return new ArrayList(anagram_map.values());
    }
}
```

## Explanation
- Create an empty HashMap to start off --> This will contain the various anagram groups in the form <k, v> : <sorted_string, ArrayList of words>

- Loop through the words array and sort the word

- Based on the sorted word, either add a new key and value to map or add to an existing list

- Repeat for the entire array of words

- Return the values of the anagram_map as a list of list of strings
