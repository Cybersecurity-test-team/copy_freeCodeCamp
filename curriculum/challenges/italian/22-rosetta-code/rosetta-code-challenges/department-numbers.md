---
id: 59f40b17e79dbf1ab720ed7a
title: I numeri dei dipartimenti
challengeType: 1
forumTopicId: 302249
dashedName: department-numbers
---

# --description--

There is a highly organized city that has decided to assign a number to each of their departments:

<ul>
  <li>Police department</li>
  <li>Dipartimento igienico-sanitario</li>
  <li>Vigili del Fuoco</li>
</ul>

Ogni dipartimento può avere un numero compreso tra 1 e 7 (inclusi).

I tre numeri dei dipartimenti devono essere unici (diversi gli uni dagli altri) e sommati devono fare numero 12.

Al Capo della Polizia non piacciono numeri dispari e vuole avere un numero pari per il suo dipartimento.

# --instructions--

Scrivi un programma che restituisca tutte le combinazioni valide come array.

```js
[2, 3, 7] [2, 4, 6] [2, 6, 4]
[2, 7, 3] [4, 1, 7] [4, 2, 6]
[4, 3, 5] [4, 5, 3] [4, 6, 2]
[4, 7, 1] [6, 1, 5] [6, 2, 4]
[6, 4, 2] [6, 5, 1]
```

# --hints--

`combinations` dovrebbe essere una funzione.

```js
assert(typeof combinations === 'function');
```

`combinations([1, 2, 3], 6)` dovrebbe restituire un array.

```js
assert(Array.isArray(combinations([1, 2, 3], 6)));
```

`combinations([1, 2, 3, 4, 5, 6, 7], 12)` dovrebbe restituire un array di lunghezza 14.

```js
assert(combinations(nums, total).length === len);
```

`combinations([1, 2, 3, 4, 5, 6, 7], 12)` dovrebbe restituire tutte le combinazioni valide.

```js
assert.deepEqual(combinations(nums, total), result);
```

# --seed--

## --after-user-code--

```js
const nums = [1, 2, 3, 4, 5, 6, 7];
const total = 12;
const len = 14;
const result = [
  [2, 3, 7],
  [2, 4, 6],
  [2, 6, 4],
  [2, 7, 3],
  [4, 1, 7],
  [4, 2, 6],
  [4, 3, 5],
  [4, 5, 3],
  [4, 6, 2],
  [4, 7, 1],
  [6, 1, 5],
  [6, 2, 4],
  [6, 4, 2],
  [6, 5, 1]
];
```

## --seed-contents--

```js
function combinations(possibleNumbers, total) {

  return true;
}
```

# --solutions--

```js
function combinations(possibleNumbers, total) {
  let firstNumber;
  let secondNumber;
  let thirdNumber;
  const allCombinations = [];

  for (let i = 0; i < possibleNumbers.length; i += 1) {
    firstNumber = possibleNumbers[i];

    if (firstNumber % 2 === 0) {
      for (let j = 0; j < possibleNumbers.length; j += 1) {
        secondNumber = possibleNumbers[j];

        if (j !== i && firstNumber + secondNumber <= total) {
          thirdNumber = total - firstNumber - secondNumber;

          if (thirdNumber !== firstNumber && thirdNumber !== secondNumber && possibleNumbers.includes(thirdNumber)) {
            allCombinations.push([firstNumber, secondNumber, thirdNumber]);
          }
        }
      }
    }
  }
  return allCombinations;
}
```
