---
id: 5900f4e81000cf542c50fffa
title: 'Problem 379: Kleinste gemeinsame Mehrfachzählung'
challengeType: 1
forumTopicId: 302041
dashedName: problem-379-least-common-multiple-count
---

# --description--

Let $f(n)$ be the number of couples ($x$, $y$) with $x$ and $y$ positive integers, $x ≤ y$ and the least common multiple of $x$ and $y$ equal to $n$.

Lasse $g$ die Summationsfunktion von $f$ sein, d.h.: $g(n) = \sum f(i)$ für $1 ≤ i ≤ n$.

You are given that $g({10}^6) = 37\\,429\\,395$.

Find $g({10}^{12})$.

# --hints--

`leastCommonMultipleCount()` should return `132314136838185`.

```js
assert.strictEqual(leastCommonMultipleCount(), 132314136838185);
```

# --seed--

## --seed-contents--

```js
function leastCommonMultipleCount() {

  return true;
}

leastCommonMultipleCount();
```

# --solutions--

```js
// solution required
```
