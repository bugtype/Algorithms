
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


## 소수 확인
```py
def isPrime(n):
    if n % 2 == 0 and n > 2: 
        return False
    for i in range(3, int(math.sqrt(n)) + 1, 2):
        if n % i == 0:
            return False
    return True
```