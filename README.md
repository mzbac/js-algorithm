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

## Find The Parity Outlier
You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier"
```js
const integers = [160, 3, 1719, 19, 11, 13, -21]

function findOutlier(integers) {
  const evens = [];
  const odds = [];
  integers.forEach(element => {
    if (Math.abs(element % 2) == 0) {
      evens.push(element);
    } else {
      odds.push(element);
    }
  });
  if (evens.length > odds.length) return odds[0];
  else return evens[0];
}


console.log(findOutlier(integers))
```

## Find next prime number
Given a List [] of n integers , find minimum mumber to be inserted in a list, so that sum of all elements of list should equal the closest prime number .
```js
function minimumNumber(numbers){
  let sum = numbers.reduce((a,b) => a + b)
  for(let i = sum; ; i++) {
    if(prime(i)) return i - sum
  }
  function prime(a) {
    if(a < 2) return false
    if(a % 2 === 0) return a === 2
    for(let i = 3; i * i < a; i += 2) {
      if(a % i === 0) return false
    }
    return true
  }
}

```
