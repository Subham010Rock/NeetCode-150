# NeetCode-150

### Array and Hashing :-
    
## 1. [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
   Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.
   
   ###### Solution--
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
   
   ###### Solution--
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

###### Solution(C++) --
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
## 4. [Group Anagrams](https://leetcode.com/problems/group-anagrams/)
Given an array of strings strs, group the anagrams together. You can return the answer in any order.<br/>
An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

###### Solution(Python)--

```
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        l=[]
        d={}
        ind=0
        for i in strs:
            s="".join(sorted(i))
            if s not in d:
                d[s]=ind
                l.append([i])
                ind+=1
            else:
                l[d[s]].append(i)
        return l
```
## 5. [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

###### Solution(C++)--

```
class Solution {
public:
    static bool comp(pair<int,int>&a,pair<int,int>&b){
        return a.second > b.second;
    }
    vector<int> topKFrequent(vector<int>& nums, int k) {
        map<int,int>m;
        for(int i=0;i<nums.size();i++){
            if(m.find(nums[i])!=m.end())
                m[nums[i]]++;
            else
                m[nums[i]]=1;
        }
        vector<pair<int,int>>v;
        for(auto& it:m){
            v.push_back(it);
        }
        sort(v.begin(),v.end(),comp);
        
        vector<int>res;
        for(int i=0;i<k;i++){
            res.push_back(v[i].first);
        }
        return res;
    }
};
```
