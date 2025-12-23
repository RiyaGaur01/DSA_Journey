## Problem Statement
Given an array of integers and a target, return indices of the two numbers such that they add up to the target.

## Approach
Use a hash map to store numbers and their indices while iterating through the array.
For each element, check if its complement (target - current number) already exists.

## Algorithm
1. Initialize an empty hash map.
2. Traverse the array using index i.
3. For each element, compute complement = target - nums[i].
4. If complement exists in the hash map, return the stored index and current index.
5. Otherwise, store the current number with its index.

## Code
```python
def twoSum(nums, target):
        seen = {}
        for i in range(len(nums)):
            num = nums[i]
            complement = target - num
            if complement in seen:
                return [seen[complement] , i]
            seen[num] = i
```
## Time & Space Complexity
- Time: O(n)
- Space: O(n)

## Mistake / Edge Case
Initially tried brute force which is slow for large inputs.
Confusing values with indices leads to incorrect indexing.
Using a list instead of a hash map makes lookup slow.

## Note
This solution returns the first valid pair found.

