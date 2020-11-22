

### 경우의 수, 순열 permutations, combinations

```py
import itertools
mylist = [1,2,3]
mypermuatation =  itertools.permutations(mylist)
myCombinations = itertools.combinations(mylist,3)
# mypermuatation =  itertools.permutations(mylist,2)
# 뒤에 숫자가 factor 갯수

for i in mypermuatation:
    print i
print("===================")
for i in myCombinations:
    print i
# (1, 2, 3)
# (1, 3, 2)
# (2, 1, 3)
# (2, 3, 1)
# (3, 1, 2)
# (3, 2, 1)
# ===================
# (1, 2, 3)
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


### n 진수 변환 코드
```py
import string
def convert(n, base):
    upper = string.ascii_uppercase
    digit = string.digits
    T = digit + upper
    q, r = divmod(n, base)
    if q == 0:
        return T[r]
    else:
        return convert(q, base) + T[r]
print convert(233, 2)
print convert(233, 8)
print convert(233, 30)
# 11101001
# 351
# 7N


import string
def convert(n, base):
    if n==0: return 0
    
    upper = string.ascii_uppercase
    digit = string.digits
    T = digit + upper
    q = n
    output = []
    
    while(q!=0):
        q, r = divmod(q, base)
        output = [T[r]]+output
    return "".join(output)

print convert(3, 2) #11
print convert(15, 16) # F
print convert(255, 16) # FF

```

### 회전

```py
def rot90(l):
  return list(zip(*l[::-1]))
def rotMinus90(l):
  return list(zip(*[x[::-1] for x in l]))

def arrayPrint(l):
  for r in l:
    print(r)
  print("===========")

a = [[1,2],[3,4]]  
b = [[1,2,3],[4,5,6],[7,8,9]]

rotated = rot90(a)
rotated2 = rotMinus90(a)
rotated3 = rot90(b)
rotated4 = rotMinus90(b)


arrayPrint(rotated)
arrayPrint(rotated2)
arrayPrint(rotated3)
arrayPrint(rotated4)
```


### Factorial 팩토리얼

```py
# 1 1 2 3 5 8
def fibo(n):
    dp = [0,1]
    for _ in range(1,n):
        dp[0], dp[1] = dp[1], dp[0]+dp[1]
    return dp[1]
    
for i in range(1,10):
    d = fibo(i)
    print(d)
    
    
def fib():
    a, b = 1, 1
    while True:
        yield a
        a, b = b, a + b
    return b
        
for index, x in enumerate(fib()):
    if index == 10:
        break
    print("%s" % x),
```

### Score of Parentheses


```py

def scoreOfParentheses(self, S):
        stack, cur = [], 0
        for i in S:
            if i == '(':
                stack.append(cur)
                cur = 0
            else:
                cur += stack.pop() + max(cur, 1)
        return cur
        
```

### n으로 표현

https://programmers.co.kr/learn/courses/30/lessons/42895?language=python3

```
S = [{N}]
    for i in range(2, 9):
        lst = [int(str(N)*i)]
        for X_i in range(0, int(i / 2)):
            for x in S[X_i]:
                for y in S[i - X_i - 2]:
                    lst.append(x + y)
                    lst.append(x - y)
                    lst.append(y - x)
                    lst.append(x * y)
                    if x != 0: lst.append(y // x)
                    if y != 0: lst.append(x // y)
        if number in set(lst):
            return i
        S.append(lst)
    return -1
```


