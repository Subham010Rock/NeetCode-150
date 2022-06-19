# NeetCode-150

## Array and Hashing :-
    
   ## 1. [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
   Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.
   
   Solution--
   ```
   class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        if len(set(nums))==len(nums):
            return False
        else:
            return True
   ```
   
   ## 2. [Valid Anagram](https://leetcode.com/problems/valid-anagram/)
   Given two strings s and t, return true if t is an anagram of s, and false otherwise.<br/>
   An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.
   
   Solution--
   ```
   class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if(len(s)!=len(t)):
            return False
        d={}
        for i in t:
            d[i]=d.get(i,0)+1
        for i in s:
            if i not in d:
                return False
            else:
                d[i]-=1
                if(d[i]==0):
                    del d[i]
        return True
    ```
