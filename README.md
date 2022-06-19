# NeetCode-150

### Array and Hashing :-
    
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

## 3. [Two Sum](https://leetcode.com/problems/two-sum/)
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.<br/>
You may assume that each input would have exactly one solution, and you may not use the same element twice.<br/>
You can return the answer in any order.

Solution(C++) --
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        map<int,int>m;
        vector<int>res;
        //map<int,int>::iterator it;
        for(int i =0;i<nums.size();i++){
            if(m.find(target-nums[i])!=m.end()){
                res.push_back(m[target-nums[i]]);
                res.push_back(i);
                break;
            }
            else{
                m[nums[i]]=i;;
            }
        }
        return res;
    }
};
```
