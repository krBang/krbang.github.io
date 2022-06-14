---
layout: post
title:  "백준 동전 0"
date:   2022-06-14 18:15:00 +0900
categories: Python Greedy Algorithm
---

[문제 동전0 11047](https://www.acmicpc.net/problem/11047)

__내 풀이__

```py
n, k = map(int, input().split())
data = []
result = 0

for i in range(n):
    data.append(int(input()))

data.sort(reverse=True)

for price in data:
    if k >= price:
        result += k // price
        k = k % price
        
print(result)
```