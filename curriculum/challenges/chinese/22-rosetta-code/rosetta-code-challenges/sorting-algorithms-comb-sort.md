---
id: 5a23c84252665b21eecc8005
title: 排序算法/Comb 排序
challengeType: 1
forumTopicId: 302313
dashedName: sorting-algorithmscomb-sort
---

# --description--

Implement a *comb sort*.

**Comb Sort** 是冒泡排序的变体。

与 Shell sort 一样，Comb Sort 增加了用于比较和交换的间隔。

将差距除以 $(1-e^{-\\varphi})^{-1} \\approx 1.247330950103979$ 效果最好，但 1.3 可能更实用。

一旦间隙小于一定数量，一些实现就使用插入排序。

变种：

<ul>
  <li>Combsort11 makes sure the gap ends in (11, 8, 6, 4, 3, 2, 1), which is significantly faster than the other two possible endings.</li>
  <li>当数据几乎排序完成（间隔很小）时，具有不同结尾的 comb 排序会变为更有效的排序方式。 间隔较低的 sort 排序并不比冒泡排序好多少。</li>
</ul>

伪代码：

<pre><b>function</b> combsort(<b>array</b> input)
  gap := input<b>.size</b> <i>//initialize gap size</i>
  <b>loop until</b> gap = 1 <b>and</b> swaps = 0
    <i>//update the gap value for a next comb. Below is an example</i>
    gap := int(gap / 1.25)
    <b>if</b> gap &#x3C; 1 
      <i>//minimum gap is 1</i>
      gap := 1
    <b>end if</b>
    i := 0
    swaps := 0 <i>//see <a href='https://rosettacode.org/wiki/Sorting_algorithms/Bubble_sort' target='_blank'>Bubble Sort</a> for an explanation</i>
    <i>//a single "comb" over the input list</i>
    <b>loop until</b> i + gap >= input<b>.size</b> <i>//see <a href='https://rosettacode.org/wiki/Sorting_algorithms/Shell_sort' target='_blank'>Shell sort</a> for similar idea</i>
      <b>if</b> input[i] > input[i+gap]
        <b>swap</b>(input[i], input[i+gap])
        swaps := 1 <i>// Flag a swap has occurred, so the</i>
            <i>// list is not guaranteed sorted</i>
      <b>end if</b>
      i := i + 1
    <b>end loop</b>
  <b>end loop</b>
<b>end function</b>
</pre>

# --instructions--

使用 Comb 排序函数对给定的数组进行排序。

# --hints--

`combSort` 应该是一个函数。

```js
assert(typeof combSort == 'function');
```

`combSort([25, 32, 12, 7, 20])` 应该返回一个数组。

```js
assert(Array.isArray(combSort([25, 32, 12, 7, 20])));
```

`combSort([25, 32, 12, 7, 20])` 应该返回 `[7, 12, 20, 25, 32]`。

```js
assert.deepEqual(combSort([25, 32, 12, 7, 20]), [7, 12, 20, 25, 32]);
```

`combSort([38, 45, 35, 8, 13])` 应该返回 `[8, 13, 35, 38, 45]`。

```js
assert.deepEqual(combSort([38, 45, 35, 8, 13]), [8, 13, 35, 38, 45]);
```

`combSort([43, 36, 20, 34, 24])` 应该返回 `[20, 24, 34, 36, 43]`。

```js
assert.deepEqual(combSort([43, 36, 20, 34, 24]), [20, 24, 34, 36, 43]);
```

`combSort([12, 33, 26, 18, 1, 16, 38])` 应该返回 `[1, 12, 16, 18, 26, 33, 38]`。

```js
assert.deepEqual(combSort([12, 33, 26, 18, 1, 16, 38]), [
  1,
  12,
  16,
  18,
  26,
  33,
  38
]);
```

`combSort([3, 39, 48, 16, 1, 4, 29])` 应该返回 `[1, 3, 4, 16, 29, 39, 48]`。

```js
assert.deepEqual(combSort([3, 39, 48, 16, 1, 4, 29]), [
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
function combSort(arr) {

}
```

# --solutions--

```js
function combSort(arr) {
  function is_array_sorted(arr) {
    var sorted = true;
    for (var i = 0; i < arr.length - 1; i++) {
      if (arr[i] > arr[i + 1]) {
        sorted = false;
        break;
      }
    }
    return sorted;
  }
  var iteration_count = 0;
  var gap = arr.length - 2;
  var decrease_factor = 1.25;

  // Until array is not sorted, repeat iterations
  while (!is_array_sorted(arr)) {
    // If not first gap
    if (iteration_count > 0)
      // Calculate gap
      gap = gap == 1 ? gap : Math.floor(gap / decrease_factor);

    // Set front and back elements and increment to a gap
    var front = 0;
    var back = gap;
    while (back <= arr.length - 1) {
      // If elements are not ordered swap them
      if (arr[front] > arr[back]) {
        var temp = arr[front];
        arr[front] = arr[back];
        arr[back] = temp;
      }

      // Increment and re-run swapping
      front += 1;
      back += 1;
    }
    iteration_count += 1;
  }

  return arr;
}
```
