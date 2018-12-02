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
