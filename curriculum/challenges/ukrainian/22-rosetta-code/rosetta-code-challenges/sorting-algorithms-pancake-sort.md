---
id: 5a23c84252665b21eecc800b
title: Алгоритми сортування/Млинцеве сортування
challengeType: 1
forumTopicId: 302315
dashedName: sorting-algorithmspancake-sort
---

# --description--

Write a function to sort an array of integers (of any convenient size) into ascending order using Pancake sorting. The function should return the sorted array.

Коротко кажучи, замість сортування окремих елементів єдина дозволена операція – це «перевертання» одного кінця списку, наприклад:

<pre>До:
<b>6 7 8 9</b> 2 5 3 4 1<br>
Після:
<b>9 8 7 6</b> 2 5 3 4 1
</pre>

Можна перевернути тільки один кінець списку. Це повинна бути нижня межа, але допустима й верхня межа, якщо її легше запрограмувати або вона краще працює, але це **повинен** бути один і той самий кінець для цілого розв'язку. (Перевернутий кінець не можна змінити довільно.)

# --hints--

`pancakeSort` має бути функцією.

```js
assert(typeof pancakeSort == 'function');
```

`pancakeSort([25, 32, 12, 7, 20])` має повернути масив.

```js
assert(Array.isArray(pancakeSort([25, 32, 12, 7, 20])));
```

`pancakeSort([25, 32, 12, 7, 20])` має повернути `[7, 12, 20, 25, 32]`.

```js
assert.deepEqual(pancakeSort([25, 32, 12, 7, 20]), [7, 12, 20, 25, 32]);
```

`pancakeSort([38, 45, 35, 8, 13])` має повернути `[8, 13, 35, 38, 45]`.

```js
assert.deepEqual(pancakeSort([38, 45, 35, 8, 13]), [8, 13, 35, 38, 45]);
```

`pancakeSort([43, 36, 20, 34, 24])` має повернути `[20, 24, 34, 36, 43]`.

```js
assert.deepEqual(pancakeSort([43, 36, 20, 34, 24]), [20, 24, 34, 36, 43]);
```

`pancakeSort([12, 33, 26, 18, 1, 16, 38])` має повернути `[1, 12, 16, 18, 26, 33, 38]`.

```js
assert.deepEqual(pancakeSort([12, 33, 26, 18, 1, 16, 38]), [
  1,
  12,
  16,
  18,
  26,
  33,
  38
]);
```

`pancakeSort([3, 39, 48, 16, 1, 4, 29])` має повернути `[1, 3, 4, 16, 29, 39, 48]`.

```js
assert.deepEqual(pancakeSort([3, 39, 48, 16, 1, 4, 29]), [
  1,
  3,
  4,
  16,
  29,
  39,
  48
]);
```

# --seed--

## --seed-contents--

```js
function pancakeSort(arr) {

}
```

# --solutions--

```js
function pancakeSort(arr) {
  for (var i = arr.length - 1; i >= 1; i--) {
    // find the index of the largest element not yet sorted
    var max_idx = 0;
    var max = arr[0];
    for (var j = 1; j <= i; j++) {
      if (arr[j] > max) {
        max = arr[j];
        max_idx = j;
      }
    }

    if (max_idx == i) continue; // element already in place

    var new_slice;

    // flip arr max element to index 0
    if (max_idx > 0) {
      new_slice = arr.slice(0, max_idx + 1).reverse();
      for (var j = 0; j <= max_idx; j++) arr[j] = new_slice[j];
    }

    // then flip the max element to its place
    new_slice = arr.slice(0, i + 1).reverse();
    for (var j = 0; j <= i; j++) arr[j] = new_slice[j];
  }
  return arr;
}
```
