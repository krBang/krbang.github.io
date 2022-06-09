---
layout: post
title:  "백준 바닥장식"
date:   2022-06-08 16:09:00 +0900
categories: Python BAEKJOON
---

[백준 바닥장식 1388](https://www.acmicpc.net/problem/1388)

DFS 사용하기 어려워서 그냥 풀리는대로 풀었다ㅠ  

```python
n, m = map(int,input().split())
deco = []
result = 0

for i in range(n):
  deco.append(input()) 

for i in range(n) :
    for j in range(m) :
        nowDeco = deco[i][j]
        if nowDeco == '|':
            if i != 0:
                if deco[i-1][j] == nowDeco:
                    continue
        elif nowDeco == '-':
            if j != 0:
                if deco[i][j-1] == nowDeco:
                    continue
        result += 1

print(result)
```