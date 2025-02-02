---
_filters:
---

# 문제 제목
[219Contains Duplicate 2](https://leetcode.com/problems/contains-duplicate-ii/description/?envType=study-plan-v2&envId=top-interview-150)

![[스크린샷 2024-12-21 오후 4.51.55.png]]
## 문제 설명
- **출처**: [LeetCode](https://leetcode.com), [Programmers](https://programmers.co.kr), etc.
- **문제 유형**: hash map
- **난이도**: (Easy,


### 문제 요약
 값이 동일한 값이 인덱스차이가 k이하면 트루 

### 제약 조건
- (예: 1 <= nums.length <= 10^4)


## 풀이 계획
1. **아이디어**: 
2. 1.딕셔너리를 만든다
	2.딕셔너리에 결과값과 index를 매치시킨다
	3.while을 돌릴때 값과 딕셔너리의값이 같을때 인덱스를 비교해서 k보다 작으면 트루
	4.값은 같지만 인덱스를 만족못하면 다시 dict[nums[i]]=i로 업데이트
	5.아니라도 업데이트
	6.끝까지 안나오면 false
   
3. **시간 복잡도**:
   - (예: O(n)

---

## 코드
```python
class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        dict={}
        for i in range(len(nums)):
            if nums[i] in dict:
                if abs(dict[nums[i]]-i)<=k:
                    return True
                else:
                    dict[nums[i]]=i
            else: 
                dict[nums[i]]=i
        return False 
