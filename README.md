# Algorithms
알고리즘 연습 및 Snippet


목차
=================
* 주의 및 생각해야 할 것들
    * [주의사항](#주의사항)
    * [생각해야할_것_풀이방식](#생각해야할_것_풀이방식)

* [CS](#CS)
    * [LRU](#LRU)
* [String](#String)
* [array](#Array)
* [Dictionary](#Dictionary)
* [Math](#Math)

## 주의사항 

- 조건식 준거에 대해서 정의하기 
    - Swift에서는 guard let
    - Method 단계적으로 정의하기 ( dateToObject, timeToInt, filterData, stringToBit, string2bit )
- Error 처리 


## 생각해야할_것_풀이방식

- 집합 ( set, union.. 등)
- 스택, 큐
- DFS, BFS
- Memorial
- 비트연산 and, or, xor, not
- Cache 알고리즘 ( LRU, FIFO, LFU )



## CS

### LRU

```py
def calc_cache(cache, string, cache_size):
    try:
        if len(cache) > cache_size:
            if cache.count(string) == 0:
                cache.pop()
                cache[0] += 1
            elif cache.count(string) == 1:
                cache.remove(string)
        else:
            if cache.count(string) == 0:
                cache[0] += 1
        cache.insert(1, string)
    except:
        cache[0] = len(cities)
    finally:
        return cache
```


## String

### replace

```py
import re
s = "Example String"
replaced = re.sub('[ES]', 'a', s)
print (replaced )

axample atring
```


## Array

### flatmap

```py
a = [1,2] + [3,4]
print (a)

[1, 2, 3, 4]

```

### zip

```py
a = [1,2]
b = [3,4]
c = [4,5,6]
print (zip(a,b))
print (zip(a,c))

[(1, 3), (2, 4)]
[(1, 4), (2, 5)]
```

### zip with index

```py
source = ['a', 'b', 'c']
for index, element in enumerate(source):
    print('%d: %s' % (index, element))

0: a
1: b
2: c
```

## Dictionary

### Tuple

```py
source = ['a', 'b', 'c']
for index, element in enumerate(source):
    print('%d: %s' % (index, element))

0: a
1: b
2: c
```

### Counter

```py
# 카운터 숫자 세기
import collections

def solution(participant, completion):
    print(collections.Counter(participant))
    answer = collections.Counter(participant) - collections.Counter(completion)
    print(collections.Counter(answer))
    return list(answer.keys())[0]

A = ["a","b","c"]
B = ["b","c"]
pr = solution(A,B)
print(pr)

Counter({'a': 1, 'c': 1, 'b': 1})
Counter({'a': 1})
a
```


## Math

### CF( highest common factor ) 최대공약수

```py

# Program to find the HCF of two Numbers
def find_hcf(num_1, num_2):
    if num_1 == 0:
        return num_2
    if num_2 == 0:
        return num_1
    # Base Case
    if num_1 == num_2:
        return num_1
    if num_1 > num_2:
        return find_hcf(num_1 - num_2, num_2)
    return find_hcf(num_1, num_2 - num_1)


def main():
    num_1 = 24
    num_2 = 48
    print('HCF of %s and %s is %s:' % (num_1, num_2, find_hcf(num_1, num_2)))

```

### LCM (  least common multiple ) 최소 공배수

```py
def find_lcm(num_1, num_2):
    max = num_1 if num_1 > num_2 else num_2
    lcm = max
    while (True):
        if ((lcm % num_1 == 0) and (lcm % num_2 == 0)):
            break
        lcm += max
    return lcm


def main():
    num_1 = 12
    num_2 = 76
    print(find_lcm(num_1, num_2))
```

### 모든 경우의 수
``` 
옷 종류가 3개
신발 종류가 2개
안경 종류가 4개

더한 곱 - 1
(3+1) * (2+1) * (4+1) -1
```


## CP

### regex

```py
# 010-1234-5678 -> 1
# 82-010-1234-5678 -> 2
# +82-010-1234-5678 -> 3
import re
def resolve(data):
    patterns = [ '^[0-9]{3}-[0-9]{4}-[0-9]{4}', '^[0-9]{2}-[0-9]{3}-[0-9]{4}-[0-9]{4}', '^\+[0-9]{2}-[0-9]{3}-[0-9]{4}-[0-9]{4}' ]
    for i in range(0, len(patterns)):
        pattern = patterns[i]
        regex = re.compile(pattern)
        mc = regex.findall(data)
        if len(mc) > 0:
            print (i + 1)
            return (i + 1)
            break

resolve("010-1234-5678")
resolve("82-010-1234-5678")
resolve("+82-010-1234-5678")
```


### collections

```py
import collections
source = ['a', 'b', 'c']

print(collections.Counter(source))
print(collections.Counter(source).keys())

# Counter({'a': 1, 'c': 1, 'b': 1})
# ['a', 'c', 'b']
```


### set, list 

```py
def d_fn(n): return (n + sum([int(x) for x in str(n)]))

S = set(range(5000))
Z = set([d_fn(n) for n in range(5000)])
print (sum(S-Z))
# 1227365


set3 = set(range(3, 1000, 3))
set5 = set(range(5, 1000, 5))

print sum(set3 | set5)

sum(list([x for x in range(1000) if x%3==0 or x%5==0]))
# set3 | set5 의 의미는 set3와 set5의 합집합입니다.
```

### count

```py
count={ x:0 for x in range(0,10) }

for x in range(1,1001):
    for i in str(x):
        count[int(i)]+=1

print(count)

from collections import defaultdict

d = defaultdict(int)
for n in range(1, 1001):
    for x in str(n):
        d[x] += 1

print(d)
```

### 8 count

```py
print str(range(1,10001))
print(str(list(range(1, 10001))).count('8'))
print str(range(1,10001)).count('8')

# [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,. ...
# 4000
# 4000

```

### 경우의 수, 순열 permutations

```py
import itertools
mylist = [1,2,3]
mypermuatation =  itertools.permutations(mylist)
# mypermuatation =  itertools.permutations(mylist,2)
# 뒤에 숫자가 factor 갯수 

for i in mypermuatation:
    print i

```

### 알파벳 출력

```py

alphabet = []
for letter in range(97,123):
    alphabet.append(chr(letter)

print(alphabet)
print([chr(letter) for letter in range(97,123)])
```




### 추천 동영상 

https://www.youtube.com/watch?v=mY1-xSmJEic

https://www.youtube.com/channel/UCW_PO0316aD16L3IcD34wPg/videos


#### Ref
https://github.com/TheAlgorithms/Python

http://pythonstudy.xyz/python/article/401-%EC%A0%95%EA%B7%9C-%ED%91%9C%ED%98%84%EC%8B%9D-Regex

https://github.com/chimpler/python-functional-guide

https://gomguard.tistory.com/114
