# Algorithms
알고리즘 연습 및 Snippet


목차
=================
* 주의 및 생각해야 할 것들
    * [주의사항](#주의사항)
    * [생각해야할_것_풀이방식](#생각해야할_것_풀이방식)

* [CS](#CS)
    * [Hash를_이용한_문제](#Hash를_이용한_문제)
    * [LRU](#LRU)
* [String](#String)
    * [n진수 만들기](#n진수_만들기)
    * [itertools를 이용한 proudct 연산](#itertools를_이용한_product)
* [array](#Array)
    * [rotation](#2D_array_rotation)
    * [roation_numpy](#2d_array_rotation_numpy)
* [Dictionary](#Dictionary)
* [Set](#Set)
* [Math](#Math)
    * [Radian](#Radian)
* [강의 추천](#강의_추천)
* [응용문제](#응용문제)


## 주의사항 

- 조건식 준거에 대해서 정의하기 
    - ~~Swift에서는 guard let~~
    - Method 단계적으로 정의하기 ( dateToObject, timeToInt, filterData, stringToBit, string2bit )
- Error 처리 
- 경우의수 생각해서 조건식 넣기 
- L,R,U,D 으로 사각형 체크방법
    - 모두 다른 단어야 한다. LURD ULPR...
    - 문자열에서 단어들의 차이가 3이여야 한다. ( 같은 단어가 있는지 체크해도 될 듯)
    - 1,3번째가 L,R이면 2,4번째는 U,D 이여야 한다


## 생각해야할_것_풀이방식

- 집합 ( set, union.. 등)
- 스택, 큐 ( Dummy 넣어서 해결해보기 / 빈값)
    - [0,0]
- DFS, BFS
- Memorial
- 비트연산 and, or, xor, not
- Cache 알고리즘 ( LRU, FIFO, LFU )
- 정렬이 이미 된 list는 이진트리가 검색이 빠름. logn



## CS

### Hash를_이용한_문제

A = [leo, kiki, eden]
B = [eden, kiki]
output = leo

```py
import collections
def solution(participant, completion):
    A = collections.Counter(participant)
    B = collections.Counter(completion)
    C = list(A-B)
    print()
    return C[0]
```


### DFS

일반적인 DFS 공식

DFS(list, current_index, 연산자,start_value, target_value)

```py
# 배열 [1,1,1,1]이 있을때 3을 구하는 방식
# 또는 3을 구하는 방식 갯수
# 연산자는 +, -만 가능
# 가능한 연산 +1, -1

def calc(list, a,b,i,target):
    global count
    
    if i >= len(list)-1:
        if(target == a+b):
            count+=1
        return 1
    calc(list, a+b, list[i+1], i+1, target)
    calc(list, a+b, -list[i+1], i+1 ,target)

calc(numbers, 0, numbers[index], index, target)
calc(numbers, 0, -numbers[index], index, target)
# calc(배열,더한값,연산자,index,taget)

```

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


### n진수_만들기

```py
def convert(n, base):                  
    T = "0123456789ABCDEF"             
    q, r = divmod(n, base)             
    if q == 0:                         
        return T[r]                    
    else:                              
        return convert(q, base) + T[r] 
                                       
                                       
print convert(233, 6)                  
```
### replace

```py
import re
s = "Example String"
replaced = re.sub('[ES]', 'a', s)
print (replaced )

axample atring
```

### itertools를_이용한_product
```py
import itertools                                             
iterable1 = 'AB'          
iterable2 = '10'
iterable3 = '#@'
s = itertools.product(iterable1, iterable2, iterable3)
for x in s:
    print(x)                                                         
# ('A', '1', '#')
# ('A', '1', '@')
# ('A', '0', '#')
# ('A', '0', '@')
# ('B', '1', '#')
# ('B', '1', '@')
# ('B', '0', '#')
# ('B', '0', '@')
                                                                    
```

### 좌측, 가운데, 우측 정렬

```py
s = 'abc'
n = 7

s.ljust(n) # 좌측 정렬
s.center(n) # 가운데 정렬
s.rjust(n) # 우측 정렬
```

### 알파벳 및 숫자 출력

```py
import string 

string.ascii_lowercase # 소문자 abcdefghijklmnopqrstuvwxyz
string.ascii_uppercase # 대문자 ABCDEFGHIJKLMNOPQRSTUVWXYZ
string.ascii_letters #대소문자 모두 abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
string.digits # 숫자 0123456789
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

### 알파벳 출력

```py

alphabet = []
for letter in range(97,123):
    alphabet.append(chr(letter)

print(alphabet)
print([chr(letter) for letter in range(97,123)])
```





## Array

### union
```py
from itertools import chain
it = chain([1,2,3],[4,5,6])
print(list(it))

# [1, 2, 3, 4, 5, 6]

```

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




### 2d_array_rotation

```py
def arrayPrint(array):
    for x in array:
        print(x)
    print("###########")

original = [[1, 2,3],
            [4, 5,6],
            [7,8,9]]

arrayPrint(original) # 원본
arrayPrint(original[::-1]) # 아래로 한칸씩 밀림
arrayPrint(original[-1::]) # 위로 한칸씩 밀림
arrayPrint(zip(*original[::-1])) # 오른쪽으로 회전 / 현재 list 객체 아님 주의

# https://stackoverflow.com/questions/8421337/rotating-a-two-dimensional-array-in-python

```

### 2d_array_rotation_numpy

```py
import numpy as np
m = np.array([[1,2,3],[4,5,6],[7,8,9]], int)
rotated = np.rot90(m)
rotated2 = np.rot90(m,axes=(1,0))
rotated3 = np.rot90(m,-1)
print(m)
print(rotated)
print(rotated2)
print(rotated3)

# [[1 2 3]
#  [4 5 6]
#  [7 8 9]]

# [[3 6 9]
#  [2 5 8]
#  [1 4 7]]

# [[7 4 1]
#  [8 5 2]
#  [9 6 3]]

# [[7 4 1]
#  [8 5 2]
#  [9 6 3]]

# https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.rot90.html
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


## Set

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

### 중복만 제거, 중복된 것만 남기기

```py
l = [1,2,2,3,3,4,5]
a = set([x for x in l if l.count(x) > 1])
b = set([x for x in l if l.count(x) == 1])

print(a)
print(b)
#set([2, 3])
#set([1, 4, 5])
```

## Math

### radian, sin, cos

```py
import math

print("exp(1.0) = ",math.exp(1))
print("log(2.78) = ",math.log(math.e))
print("log10(10,10) = ",math.log(10,10))
print("sqrt = ",math.sqrt(4.0))
 
print("sin(PI/2) = ",math.sin(math.pi / 2))
print("cos(PI/2) = ",math.cos(math.pi / 2))
print("tan(PI/2) = ",math.tan(math.pi / 2))
print("degrees(1.57) = ",math.degrees(1.57))
print("radians(90) = ",math.radians(90)
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

## 응용문제

### zip문제 arr2개 카카오 비밀지도

```py

def solution(n, arr1, arr2):
    answer = []
    for i,j in zip(arr1,arr2):
        a12 = str(bin(i|j)[2:])
        a12=a12.rjust(n,'0')
        a12=a12.replace('1','#')
        a12=a12.replace('0',' ')
        answer.append(a12)
    return answer

```


## 강의_추천 

#### 추천 동영상 

sk 알고리즘
https://www.youtube.com/results?search_query=sk+%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98

https://www.youtube.com/watch?v=mY1-xSmJEic

https://www.youtube.com/channel/UCW_PO0316aD16L3IcD34wPg/videos


#### Ref
https://github.com/TheAlgorithms/Python

http://pythonstudy.xyz/python/article/401-%EC%A0%95%EA%B7%9C-%ED%91%9C%ED%98%84%EC%8B%9D-Regex

https://github.com/chimpler/python-functional-guide

https://gomguard.tistory.com/114
