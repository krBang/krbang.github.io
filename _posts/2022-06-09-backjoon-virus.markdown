---
layout: post
title:  "백준 바이러스"
date:   2022-06-08 16:09:00 +0900
categories: Python BAEKJOON
---

[백준 바이러스 2606](https://www.acmicpc.net/problem/2606)

DFS 사용해서 풀었다.

인접한 노드를 구하는게 오히려 힘들었다.
* defaultdict 잘 알아두기!

```py
from collections import defaultdict

def dfs(node):
    global result
    visit[node] = True
    if node != 1:
        result += 1
    for i in d[node]:
        if not visit[i]:
            dfs(i)

n = int(input())
con = int(input())
d = defaultdict(set)
visit = [False] * 101
result = 0

for i in range(con):
    node1, node2 = map(int, input().split())
    d[node1].add(node2)
    d[node2].add(node1)

dfs(1)
print(result)
```


참고 
[딕셔너리 초기값 지정](https://velog.io/@areum0921/defaultdict-%EB%94%95%EC%85%94%EB%84%88%EB%A6%AC-%EC%B4%88%EA%B8%B0%EA%B0%92-%EC%A7%80%EC%A0%95)
