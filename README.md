# Algorithms
알고리즘 연습 및 Snippet


## 알고리즘 테스트에서 주의사항 

- 조건식 준거에 대해서 정의하기 
    - Swift에서는 guard let
    - Method 단계적으로 정의하기 ( dateToObject, timeToInt, filterData )
- Error 처리 


## 알고리즘 테스트에서 생각해야할 것들 

- 집합 ( set, union.. 등)
- 스택, 큐
- DFS, BFS
- Memorial



## Array

### flatmap

```py
a = [1,2] + [3,4]
print (a)

[1, 2, 3, 4]

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




#### Ref
https://github.com/TheAlgorithms/Python

http://pythonstudy.xyz/python/article/401-%EC%A0%95%EA%B7%9C-%ED%91%9C%ED%98%84%EC%8B%9D-Regex

https://github.com/chimpler/python-functional-guide

