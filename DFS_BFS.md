

순회 관련

- 감시피하기 https://www.acmicpc.net/problem/18428

```py
# 상,하,좌,우 움직이는 배열
dx = [1,-1, 0, 0]
dy = [0, 0, 1, -1]



# 직선 방향 확인 함수
def check_S(x,y):
  for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
    # 직선 방향으로 확인
    while 0<= nx < n and 0<= ny < n and graph[nx][ny] !='O':
      if graph[nx][ny] == 'S':
        # 감시가능하다
        return True            
      else:        
        # T 나 X으면 계속 탐색
        nx += dx[i]
        ny += dy[i]
  # 감시 불가능하다
  return False
```
