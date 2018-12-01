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
