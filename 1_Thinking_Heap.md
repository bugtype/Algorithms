
# Heap

- 힙을 이용하여 구할 수 있는 알고리즘

## 특징

- 삽입 (logN)
  - 마지막 노드에 넣어서 비교
- 삭제 (logN)
  - root node 삭제 후, root 노드에 이동하여 연산
  https://gmlwjd9405.github.io/2018/05/10/data-structure-heap.html

### 1. 중간값 구하기
  - max heap과 min heap 이용.
   - https://www.crocus.co.kr/625


```
import sys
import heapq

numbers = int(input())
max_heap = []
min_heap = []

for _ in range(numbers):
    num = int(input())
    if len(max_heap) == len(min_heap):
        heapq.heappush(max_heap, (-num, num))
    else:
        heapq.heappush(min_heap, (num, num))
    
    if min_heap and max_heap[0][1] > min_heap[0][1]:
        temp_max = heapq.heappop(max_heap)[1]
        temp_min = heapq.heappop(min_heap)[1]
        heapq.heappush(max_heap, (-temp_min, temp_min))
        heapq.heappush(min_heap, (temp_max, temp_max))
    print(max_heap[0][1])
```
   
### 2. n번째 작은값 or 큰 값 구하기
  - 5번째 작은 값을 원할 경우, min heap 에서 length 5로해서 넣었다가 뺏다가 하기.  
  - 10번째 큰 값을 원할 경우, max heap 에서 length 10로해서 넣었다가 뺏다가 하기.

### 3. 우선순위가 있는 요청 처리
  - 디스크 컨트롤러
  - https://programmers.co.kr/learn/courses/30/lessons/42627
  - https://mungto.tistory.com/15
  

###  4. 이중 우선순위 큐
  - https://programmers.co.kr/learn/courses/30/lessons/42628?language=python3
  - max heap과 min heap 이용.
 
 ```
from heapq import heappush, heappop

def solution(arguments):
    max_heap = []
    min_heap = []
    for arg in arguments:
        if arg == "D 1":
            if max_heap != []:
                heappop(max_heap)
                if max_heap == [] or -max_heap[0] < min_heap[0]:
                    min_heap = []
                    max_heap = []
        elif arg == "D -1":
            if min_heap != []:
                heappop(min_heap)
                if min_heap == [] or -max_heap[0] < min_heap[0]:
                    max_heap = []
                    min_heap = []
        else:
            num = int(arg[2:])
            heappush(max_heap, -num)
            heappush(min_heap, num)
    if min_heap == []:
        return [0, 0]
    return [-heappop(max_heap), heappop(min_heap)]
```
