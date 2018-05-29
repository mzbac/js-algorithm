# js-algorithm

## Quick sort
```js

const unSort = [4, 3, 1, 5, 6, 7, 8, 2, 5, 1];

function quickSort(arr) {
  if (arr.length <= 1) return arr;
  const tail = arr.pop();
  const smaller = arr.filter((e) => e <= tail);

  const bigger = arr.filter((e) => e > tail);

  return quickSort(smaller)
    .concat([tail])
    .concat(quickSort(bigger));
}

console.log(quickSort(unSort));

```