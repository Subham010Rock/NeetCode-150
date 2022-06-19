# NeetCode-150

## Array and Hashing :-
    
   ## [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
   Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.
   
   Solution-
   ```
   class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        if len(set(nums))==len(nums):
            return False
        else:
            return True
   ```
