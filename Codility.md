### Binary gap

```py
def solution(N):
    b = bin(N)[2:]
    maxCount = 0
    count = 0
    for x in b:
        if int(x) is 1:
            maxCount = count if count > maxCount else maxCount
            count=0
        else:
            count+=1
    return maxCount
```
