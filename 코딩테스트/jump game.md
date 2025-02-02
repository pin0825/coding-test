_filters:
---
# 🏆 Coding Test Log - {{date}}

## 📌 Problem Information
- **Title**:  [55. Jump Game](https://leetcode.com/problems/jump-game/)
- **Source**: [[55. Jump Game](https://leetcode.com/problems/jump-game/)
- **Difficulty**: ( / Medium)  
- **Category**: string/array

## 🧠 Approach
- 1.measure maxreach, on each stage, and if in specific stage, maxreach is longer than the thing, change it.
	2.if its less then i , return false
	3.if its bigger than n-1: return true
<img width="693" alt="스크린샷 2025-02-02 오후 7 29 35" src="https://github.com/user-attachments/assets/1f2102cd-dafa-43bf-9bb3-8b2c041f2697" />


  
-  

## 🔍 Algorithm Analysis
- **Algorithm Used**:  
- **Time Complexity**: O(n)  
- **Space Complexity**: O(n)  

## 💻 Code
```python
# Paste your solution here
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        maxReach = 0  
        n = len(nums)
        for i in range(n):
            if i > maxReach:
                return False
            maxReach=max(maxReach,i+nums[i])
            if maxReach>=n-1:
                return True
        return False


        
