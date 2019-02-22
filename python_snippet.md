
### 경우의수 뽑기

```py
import itertools
mylist = [1,2,3]
mypermuatation =  itertools.permutations(mylist)
# mypermuatation =  itertools.permutations(mylist,2)
# 뒤에 숫자가 factor 갯수 

for i in mypermuatation:
    print i
```

### 경우의수 갯수 nCr, nPr

```py
import math

#nCr
def nCr(n,r):
    f = math.factorial
    return f(n) // (f(r) * f(n-r))
#nPr
def nPr(n,r):
    f = math.factorial
    return f(n) // f(n-r)

print( nCr(4,2) ) # 6
print( nPr(4,2) ) # 12
```


### 소수 확인
```py
def isPrime(n):
    if n % 2 == 0 and n > 2: 
        return False
    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True
```

### Dictionary sort

```py
from operator import itemgetter
users = [
    {'name':'bugtype', 'age': 34},
    {'name':'augtype', 'age': 34},
    {'name':'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 24},
    {'name': 'bugtype', 'age': 14},
    {'name': 'dugtype', 'age': 14},
    {'name': 'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 34},

]
for x in sorted(users, key=itemgetter('name','age')):
    print(x)
```


## Dictionary sort

```py
from operator import itemgetter
users = [
    {'name':'bugtype', 'age': 34},
    {'name':'augtype', 'age': 34},
    {'name':'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 24},
    {'name': 'bugtype', 'age': 14},
    {'name': 'dugtype', 'age': 14},
    {'name': 'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 34},

]
for x in sorted(users, key=itemgetter('name','age')):
    print(x)
```



### heapq 제일 큰 숫자, 제일 작은숫자 구하기

```py
import heapq

numbers = [1, 3,5, 10, 333, 12, 44, 232, 11, 2]
users = [
    {'name':'bugtype', 'age': 100},
    {'name':'augtype', 'age': 34},
    {'name':'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 24},
    {'name': 'bugtype', 'age': 14},
    {'name': 'dugtype', 'age': 14},
    {'name': 'bugtype', 'age': 34},
    {'name': 'bugtype', 'age': 34},

]
print( heapq.nlargest(3,numbers) ) #[333, 232, 44]
print( heapq.nsmallest(3,numbers) ) #[1, 2, 3]

print( heapq.nlargest(3,users, key=lambda user:user['age']) ) #[333, 232, 44]
print( heapq.nsmallest(3,users, key=lambda user:user['age']) ) #[1, 2, 3]

```

### 그래프 만들기 x->y Grpah 

```py
from collections import defaultdict
# 그래프 만들기
graph = defaultdict(list)
for e in edge:
    graph[e[0]].append(e[1])
    graph[e[1]].append(e[0])
print(graph)
# defaultdict(<class 'list'>, {3: [6, 4, 2, 1], 6: [3], 4: [3, 2], 2: [3, 1, 4, 5], 1: [3, 2], 5: [2]})
```