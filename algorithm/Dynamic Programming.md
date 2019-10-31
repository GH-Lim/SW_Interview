# Dynamic Programming

## DP 란?

큰 문제를 더 작은 단위의 문제로 나누어 풀어가는 기법

ex) Knapsack Problem, 2 X N 종이 붙이기 등의 문제에 활용

참고 = https://www.acmicpc.net/problem/1793 

### 구현 방식

- Top - down 방식 : 상위 문제를 풀면서 하위 문제들을 결합하여 최종적으로 최적해를 구한다.
  - Memoization : 같은 하위 문제를 가지고 있다면 그 최적해를 저장해서 사용할 수 있다. 이 경우 하위 문제 수가 기하급수적으로 늘어날 때 유리하다.
- Bottom - up 방식 : top - down 방식과는 반대로 하위 문제들로 상위 문제의 최적해를 구한다.

예시 : 피보나치 수열의 경우

```python
# top down
fib = [0] * n # 메모이제이션 공간
def f(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    if fib[n]: # 만약 fib[n] 이 값을 가지고 있다면
        return fib[n] # 그 값을 가져온다
    else: # 아니라면
        fib[n] = f(n - 2) + f(n - 1) # 작은 문제로 분할!
        return fib[n]
```

```python
# bottom top
fib = [0] * n
def f(n):
    fib[0] = 0
    fib[1] = 1
    for i in range(2, n + 1):
        fib[i] = fib[i - 2] + fib[i - 1]
    return fib[n - 1]
```

만약 재귀로 구현한다면

```python
def f(n):
    if n <= 1:
        return n
    else:
        return f(n-1) + f(n-2)
```

f(5) 를 구하기 위해서는 f(4) 와 f(3)을 구해야하는데

여기서 f(5)에서 호출된 f(4)를 구하려면 다시 f(3) 과 f(2)를 호출해야하고

f(4)에서 호출된 f(3)을 구하기 위해 f(2)과 f(1)을 호출해야 한다.

이런식으로 총 9번의 호출을 일으킨다.

숫자가 작을 때는 문제가 없지만 숫자가 커진다면 시간복잡도와 공간복잡도가 exponential 하게 증가하게 된다.

