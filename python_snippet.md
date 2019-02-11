
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

### ref

코딩도장
프로그래머스
