---
_filters:
---
![[스크린샷 2024-12-21 오후 2.27.36.png]]
# 문제 제목
[49group anagrams](https://leetcode.com/problems/group-anagrams/description/?envType=study-plan-v2&envId=top-interview-150)
## 문제 설명
- **출처**: [LeetCode](https://leetcode.com), [Programmers](https://programmers.co.kr), etc.
- **문제 유형**: (hash map)
- **난이도**: Medium,


### 문제 요약
 **입력**:  
 **출력**: (예: nums 배열의 두 요소의 합이 target이 되는 인덱스 반환)
- 
![[스크린샷 2024-12-21 오후 2.27.42.png]]
### 제약 조건
- (예: 1 <= nums.length <= 10^4)
-


## 풀이 계획
1. *아이디어: 
2. 차피 각값을 기준에 따라 소트하면 숫자나 문자가 같을시에 같은값이 되서 dict으로 묶음 그리고 sort 값에따라 [sort]=값 이런식으로 붙이고 한번에 호출하는거지 
	하지만 빈건 따로 만들어줘야됨
   - 
2. **접근 방식**:
   - 각소팅한 값을 dict에 넣고 같은 문자로이루어져잇으면 append 그리고 list로 반환
3. **시간 복잡도**:
   - O(n)

---

## 코드
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        anagram_dict = defaultdict(list)
        for s in strs:
            sorted_s=''.join(sorted(s))
            if sorted_s not in anagram_dict:
                anagram_dict[sorted_s]=[]
            anagram_dict[sorted_s].append(s)
        return list(anagram_dict.values())
