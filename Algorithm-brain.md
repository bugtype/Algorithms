

### 문자열 거꾸로

- s[first], s[last] = s[last], s[first]
  - python에서 string은 immutable이라서 안된다. str[::-1] 또는 reversed() 쓰기
  - https://ledgku.tistory.com/54

#### 순열 관련

- 비어있는 거 찾는 문제
  - 합계 구해서 빼기

#### 중복 관련

- ^ 연산자 이용


#### 합계

- preSums 활용


#### 곱하는 거

- 음수X음수


#### Count

- pre count (pre sums) 활용

### 2개 더해서 타겟 구하기

- hash를 이용하면 N으로 처리 가능하다.
- 음의 정수도 포함되는지 확인하자.

```python
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        
        h = {}
        for i, num in enumerate(nums):
            n = target - num
            if n not in h:
                h[num] = i
            else:
                return [h[n], i]
```


### 삼각형 만들기

- 정렬해서 풀어야 하는지 생각해보기
- 조건이 3가지가 있다면, 정렬해서 불필요한 조건을 없앨수도 있다.
