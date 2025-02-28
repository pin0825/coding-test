---
_filters:
---
[jump game 2](https://leetcode.com/problems/jump-game-ii/description/?envType=study-plan-v2&envId=top-interview-150)
# 문제 제목
![[스크린샷 2024-12-20 오후 3.36.50.png]]

## 문제 설명
- **출처**: [LeetCode](https://leetcode.com), [Programmers](https://programmers.co.kr), etc.
- **문제 유형**: (예: 배열, 그래프, DP, 문자열)
- **난이도**: (Easy, Medium, Hard)


### 문제 요약
- **입력**: (예: 정수 배열 nums와 정수 target)
- **출력**: (예: nums 배열의 두 요소의 합이 target이 되는 인덱스 반환)

### 제약 조건
- (예: 1 <= nums.length <= 10^4)



## 풀이 계획
1. **아이디어**: 
   - (예: 투 포인터를 사용해 정렬된 배열에서 합 계산)
2. **접근 방식**:
   - (예: 배열을 순회하면서 조건에 맞는 값을 찾음)
3. **시간 복잡도**:
   - (예: O(n), O(n^2), O(log n))

---

## 코드
```python
class Solution:
    def jump(self, nums: List[int]) -> int:
        max_reach = 0
        jumps = 0
        current_end = 0
        farthest = 0
        for i in range (len(nums)-1):
            farthest=max(farthest, farthest+i+nums[i])
            
            if i==current_end:
                jumps+=1
                current_end=farthest
                
            if current_end>=len(nums)-1:
                break
        return jumps
        