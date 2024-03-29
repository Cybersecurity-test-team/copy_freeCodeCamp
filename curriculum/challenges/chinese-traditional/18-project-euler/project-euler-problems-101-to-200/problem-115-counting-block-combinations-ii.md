---
id: 5900f3df1000cf542c50fef1
title: '問題 115：計數塊組合 II'
challengeType: 1
forumTopicId: 301741
dashedName: problem-115-counting-block-combinations-ii
---

# --description--

A row measuring `n` units in length has red blocks with a minimum length of `m` units placed on it, such that any two red blocks (which are allowed to be different lengths) are separated by at least one black square.

讓填充計數函數，$F(m, n)$，表示可以填充的行數。

例如， $F(3, 29) = 673135$，$F(3, 30) = 1089155$。

就是說，對於 m = 3，可以看出 n = 30 是函數結果超過 100 萬的最小 n 值。

同樣，對於 m = 10，可以驗證 $F(10, 56) = 880711$ 和 $F(10, 57) = 1148904$。即函數第一次超過 100 萬的 n 最小值爲 57。

對於 m = 50，找到最小值 `n` 的值，讓函數第一次超過 100 萬。

**注意：** 這是問題 114 的一個困難版本。

# --hints--

`countingBlockTwo()` 應該返回 `168`。

```js
assert.strictEqual(countingBlockTwo(), 168);
```

# --seed--

## --seed-contents--

```js
function countingBlockTwo() {

  return true;
}

countingBlockTwo();
```

# --solutions--

```js
// solution required
```
