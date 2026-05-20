# Contains Duplicates | Blind 75 #1

Given an integer array nums, return true if any value appears more than once in the array, otherwise return false.

## Examples

**Example 1:**

    Input: nums = [1, 2, 3, 3]
    
    Output: true


**Example 2:**

    Input: nums = [1, 2, 3, 4]
    
    Output: false


## Thought Process

- The premise of the problem is basically that we need to determine uniqueness
- If we consider data structures, the one that comes to mind when considering uniqueness is the set
- Since a set never contains duplicates, we can take advantage of this to determine if our array has duplicates

## My Solution

```java
class Solution {
    public boolean hasDuplicate(int[] nums) {

        // Set to store the elements of the array
        HashSet<Integer> num_set = new HashSet<>();

        // Loop through array, attempt to add element to set
        for(int num : nums) {

            // If the element wasn't added to set, then it's a duplicate
            if(!(num_set.add(num))) {
                return true;
            }
        }

        // We made it through the entire array without encountering a duplicate
        return false;
    }
}
```

## Explanation

- Initialize an empty HashSet to start --> this will be where we store our array elements

- Loop through the passed in array and add each element to the HashSet

- As you add an element, check the return value of adding it to the HashSet
    - If the return value is true --> Successfully added to HashSet --> Unique element so far
    - If the return value is false --> Didn't add to HashSet because it was already present in the set --> Duplicate found
    
- If we looped through the entire array and were able to add all elements to the HashSet, then no duplicates
