---
layout: post
title:  "백준 ATM"
date:   2022-06-13 15:15:00 +0900
categories: Python Greedy Algorithm
---

[문제 백준 13399](https://www.acmicpc.net/problem/11399)

__내 풀이__
```py
n = int(input())
data = list(map(int, input().split()))

data.sort()
result = 0
sum = 0

for i in range(n):
    result += sum + data[i]
    sum += data[i]

print(result)
```
