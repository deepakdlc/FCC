https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/steamroller/

## [MY SOLUTIONS]

```JS
function steamrollArray(arr) {
  // I'm a steamroller, baby
  let newArr = [];

  for(let i=0; i<arr.length; i++){
    if(Array.isArray(arr[i])){
      newArr = newArr.concat(steamrollArray(arr[i]));
    }
    else{
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

steamrollArray([1, [2],[[3]]]);

```

## [OTHERS]

### Advance
```js
function steamrollArray(arr) {
  return arr.toString()
    .replace(',,', ',')       // "1,2,,3" => "1,2,3"
    .split(',')               // ['1','2','3']
    .map(function(v) {
      if (v == '[object Object]') { // bring back empty objects
        return {};
      } else if (isNaN(v)) {        // if not a number (string)
        return v;
      } else {
        return parseInt(v);         // if a number in a string, convert it
      }
    });
}
```

### Intermediate
```js
function steamrollArray(arr) {
  let flat = [].concat(...arr);
  return flat.some(Array.isArray) ? steamrollArray(flat) : flat;
}

flattenArray([1, [2], [3, [[4]]]]);
```

### Basic
```js
function steamrollArray(arr) {
  var flattenedArray = [];

  // Create function that adds an element if it is not an array.
  // If it is an array, then loops through it and uses recursion on that array.
  var flatten = function(arg) {
    if (!Array.isArray(arg)) {
      flattenedArray.push(arg);
    } else {
      for (var a in arg) {
        flatten(arg[a]);
      }
    }
  };

  // Call the function for each element in the array
  arr.forEach(flatten);
  return flattenedArray;
}

// test here
steamrollArray([1, [2], [3, [[4]]]]);
```
