---
id: 5900f3ee1000cf542c50ff00
title: 'Завдання 130: складені числа з властивістю простих реп’юнітів'
challengeType: 1
forumTopicId: 301758
dashedName: problem-130-composites-with-prime-repunit-property
---

# --description--

Число, що повністю складається з одиниць, називається реп’юнітом. Визначимо, що $R(k)$ є реп’юнітом довжиною $k$. Наприклад, $R(6) = 111111$.

Дано, що $n$ є натуральним числом і $НСД(n, 10) = 1$. Можна побачити, що завжди існує значення $k$, за якого $R(k)$ ділиться на $n$ без остачі. Нехай $A(n)$ буде найменшим таким значенням $k$; наприклад, $A(7) = 6$ та $A(41) = 5$.

Дано, що для всіх простих чисел $p > 5$, число $p − 1$ ділиться на $A(p)$ без остачі. Наприклад, коли $p = 41, A(41) = 5$, а 40 ділиться на 5 без остачі.

Однак існують рідкісні складені значення, для яких діє ця умова. Перші п’ять прикладів: 91, 259, 451, 481 та 703.

Знайдіть суму перших двадцяти п’яти складених значень $n$, за яких $НСД (n, 10) = 1$ й $n − 1$ ділиться на $A(n)$ без остачі.

# --hints--

`compositeRepunit()` має повернути `149253`.

```js
assert.strictEqual(compositeRepunit(), 149253);
```

# --seed--

## --seed-contents--

```js
function compositeRepunit() {

  return true;
}

compositeRepunit();
```

# --solutions--

```js
// solution required
```
