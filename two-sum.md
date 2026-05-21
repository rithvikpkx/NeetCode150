# Two Sum | Blind 75 #3

Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.

## Examples

**Example 1:**

    Input: nums = [2,7,11,15], target = 9
    
    Output: [0,1]


**Example 2:**

    Input: nums = [3,2,4], target = 6
    
    Output: [1,2]


## Thought Process

- The premise is basically that we need to somehow pick up a value and see if we can find the desired value in the rest of the array
- Since there's some sort of lookup involved, we can use a map to map values to indices
- The brute force method exists but it's most definitely not the best way to do it

## My Solution

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> visited = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int desired = target - nums[i];

            if (visited.containsKey(desired)) {
                return new int[] {visited.get(desired), i};
            }

            visited.put(nums[i], i);
        }
        return null;
    }
}
```

## Explanation

- Initialize an empty HashMap. This will contain the array elements we have visited in the form `<k, v>` : `<value, index>`.

- Loop through the passed in array.

- Calculate `desired_val = target - curr_num` for the current array element.

- Search the HashMap for `desired_val`.
    - If the HashMap contains it, then return the index found in the HashMap for the value and the index of the current num.
    - If the HashMap doesn't contain it, then add the curr_num into the map and move on.

- Repeat this process. You are guaranteed to find a matching two sum.
