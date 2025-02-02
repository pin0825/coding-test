---
_filters:
---
[57. Insert Interval](https://leetcode.com/problems/insert-interval/)

![[스크린샷 2024-12-22 오후 4.59.25.png]]
# 문제 제목
## 문제 설명
- **출처**: [LeetCode](https://leetcode.com), [Programmers](https://programmers.co.kr), etc.
- **문제 유형**: interval
- **난이도**:  Medium


### 문제 요약
- **입력**: (예: 정수 배열 n
- **출력**: 

### 제약 조건
- (예: 1 <= nums.length <= 10^4)


## 풀이 계획
1. **아이디어**: 
2. .append to new list the lists that (intervals[1 ]<newinterval[0]) cuz no shared part
	2.and while untill newinterval[1]<interval[0],  using max and min fuctions, comparing min and each intervals[][0] and max each intevals[1] and append to list
	3.append the rest lists to new list and done
   - (예: 투 포인터를 사용해 정렬된 배열에서 합 계산)
4. **시간 복잡도**:
   - (예: O(n),)

---

## 코드
```python
from typing import List

class Solution:
    def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
        result = []
        i = 0
        n = len(intervals)

        # Add all intervals that come before the new interval
        while i < n and intervals[i][1] < newInterval[0]:
            result.append(intervals[i])
            i += 1

        # Merge overlapping intervals
        while i < n and intervals[i][0] <= newInterval[1]:
            newInterval[0] = min(newInterval[0], intervals[i][0])
            newInterval[1] = max(newInterval[1], intervals[i][1])
            i += 1
        result.append(newInterval)

        # Add the rest of the intervals
        while i < n:
            result.append(intervals[i])
            i += 1

        return result

