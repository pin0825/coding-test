---
_filters:
---
---
_filters:
---
# 🏆 Coding Test Log - {{02-02-2025}}

## 📌 Problem Information
- **Title**:  [122. Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)
- **Source**: [122. Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)
- **Difficulty**: (Medium)  
- **Category**: (Array / String)  
![[스크린샷 2025-02-02 오후 6.47.05.png]]
## 🧠 Approach
1.during the loop, compare previous one and latter one, if latter one is bigger, add the profit to the total.
2change pr_p=>latter one, and if latter one is smaller than the next one, change pr_p=>next one.
## 🔍 Algorithm Analysis
- **Algorithm Used**:  
- **Time Complexity**: O(n)  
- **Space Complexity**: O(n)  

## 💻 Code
```python
# Paste your solution here
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        pr_p=prices[0]
        total=0
        profit=0
        for price in prices:
            if price<pr_p:
                pr_p=price
            if price>pr_p:
                profit=price-pr_p
                total+=profit
                pr_p=price
            
            
        return total 
