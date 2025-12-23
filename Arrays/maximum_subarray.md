## Problem Statement
Given an integer array nums, find the subarray with the largest sum, and return its sum.

## Intuition
At each position in the array, we track the sum of the best subarray ending at that position.
If adding the current element to the previous sum increases the total, we continue the subarray.
If the previous sum becomes negative, it hurts future sums, so we discard it and start a new subarray.
By continuously comparing the current subarray sum with the maximum sum seen so far, we ensure that the best possible contiguous subarray is captured.

A negative running sum is useless, so we drop it and start fresh.

## Approach
Kadane’s Algorithm is used to track the maximum subarray ending at each index.

## Algorithm
1. Initialize current_sum and max_sum with the first element.
2. Traverse the array from the second element.
3. Update current_sum = max(current element, current_sum + element).
4. Update max_sum if current_sum is greater.
5. Return max_sum.

## Code
```python
def maxSubArray(nums):
    current_sum = nums[0]
    max_sum = nums[0]

    for i in range(1, len(nums)):
        current_sum = max(nums[i], current_sum + nums[i])
        max_sum = max(max_sum, current_sum)

    return max_sum
```

## Time & Space Complexity
- Time: O(n)
- Space: O(1)

## Mistake / Edge Case
Initializing sums with 0 fails for all-negative arrays.
Resetting the running sum without understanding the logic leads to incorrect reasoning.
Confusing current subarray sum with global maximum causes wrong results.
