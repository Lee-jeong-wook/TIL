# Greedy(그리디 알고리즘)
현재 최적의 값을 선택하여 가장 적합한 결과를 도출하는 알고리즘
### 조건
현재 최적값이 다음 선택에 무관해야함
### 예시
```
import sys
sys.setrecursionlimit(1000000)

NK = input()
NKV = NK.split()
N = int(NKV[0])
K = int(NKV[1])
ip = []
cnt = 0
for i in range(N):
    ip.append(int(input()))

for i in range(N):
    cnt += K // ip[len(ip) - i - 1]
    K = K % ip[len(ip) - i - 1]
print(cnt)
```