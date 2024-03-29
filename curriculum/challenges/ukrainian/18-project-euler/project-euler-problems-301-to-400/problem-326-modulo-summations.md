---
id: 5900f4b21000cf542c50ffc5
title: 'Завдання 326: суми модулів'
challengeType: 1
forumTopicId: 301983
dashedName: problem-326-modulo-summations
---

# --description--

Нехай $a_n$ буде послідовністю, рекурсивно заданою $a_1 = 1$, $\displaystyle a_n = \left(\sum_{k = 1}^{n - 1} k \times a_k\right)\bmod n$.

Тож першими 10 елементами $a_n$ є: 1, 1, 0, 3, 0, 3, 5, 4, 1, 9.

Нехай $f(N, M)$ представляє кількість пар $(p, q)$, за яких:

$$ 1 \le p \le q \le N \\; \text{та} \\; \left(\sum_{i = p}^q a_i\right)\bmod M = 0$$

Можна помітити, що $f(10, 10) = 4$ з парами (3,3), (5,5), (7,9) та (9,10).

Також дано, що $f({10}^4, {10}^3) = 97\\,158$.

Знайдіть $f({10}^{12}, {10}^6)$.

# --hints--

`moduloSummations()` має повернути `1966666166408794400`.

```js
assert.strictEqual(moduloSummations(), 1966666166408794400);
```

# --seed--

## --seed-contents--

```js
function moduloSummations() {

  return true;
}

moduloSummations();
```

# --solutions--

```js
// solution required
```
