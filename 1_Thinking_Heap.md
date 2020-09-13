
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
   
### 2. n번째 작은값 or 큰 값 구하기
  - 5번째 작은 값을 원할 경우, min heap 에서 length 5로해서 넣었다가 뺏다가 하기.  
  - 10번째 큰 값을 원할 경우, max heap 에서 length 10로해서 넣었다가 뺏다가 하기.

### 3. 우선순위가 있는 요청 처리
  - 디스크 컨트롤러
  - https://programmers.co.kr/learn/courses/30/lessons/42627
  - https://mungto.tistory.com/15
