# Блок 2: Python

В данном блоке представлены решения алгоритмических задач на Python.  
Для каждой задачи приведён код и краткая оценка сложности по времени и памяти.

---

## Задание 1: Изоморфизмы

```python
def is_isomorphic(s, t):
    if len(s) != len(t):
        return False

    s_to_t = {}
    t_to_s = {}

    i = 0
    while i < len(s):
        cs = s[i]
        ct = t[i]

        if cs in s_to_t:
            if s_to_t[cs] != ct:
                return False
        else:
            if ct in t_to_s:
                return False
            s_to_t[cs] = ct
            t_to_s[ct] = cs

        i += 1

    return True

---

Временная сложность: O(n)
Пространственная сложность: O(n)

---

## Задание 2: Натуральная последовательность

```python
def missing_number(nums):
    n = len(nums) + 1
    expected_sum = n * (n + 1) // 2
    actual_sum = sum(nums)
    return expected_sum - actual_sum
---

Временная сложность: O(n)
Пространственная сложность: O(1)

---

## Задание 3: Факторизация 

```python
def prime_factors(n):
    factors = []
    divisor = 2

    while n > 1:
        while n % divisor == 0:
            factors.append(divisor)
            n //= divisor
        divisor += 1

    return factors

---

Временная сложность: O(√n)
Пространственная сложность: O(k), где k — количество простых множителей

---

##








