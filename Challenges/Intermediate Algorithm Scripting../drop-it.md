https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/drop-it

## [MY SOLUTIONS]

```JS
function dropElements(arr, func) {
  // Drop them elements.
  let copiedArr = arr.slice();
  
  for(let item of arr){
    if(!func(item)){
      copiedArr.shift();
    }
    else{
      break;
    }
  }
  
  return copiedArr;
}

dropElements([1, 2, 3, 4], function(n) {return n >= 3; });
```

## [OTHERS]

### Advance Code
```js
function dropElements(arr, func) {
  while(arr.length > 0 && !func(arr[0])) {
    arr.shift();
  }
  return arr;
}

// test here
dropElements([1, 2, 3, 4], function(n) {return n >= 3;});
```
### Intermediate
```js
  function dropElements(arr, func) {
  return arr.slice(arr.findIndex(func) >= 0 ? arr.findIndex(func): arr.length, arr.length);
}

// test here
dropElements([1, 2, 3, 4], function(n) {return n >= 3;});
```
### Basic
```js
function dropElements(arr, func) {
  // drop them elements.
  var times = arr.length;
  for (var i = 0; i < times; i++) {
    if (func(arr[0])) {
      break;
    } else {
      arr.shift();
    }
  }
  return arr;
}

// test here
dropElements([1, 2, 3, 4], function(n) {return n >= 3;})
```
