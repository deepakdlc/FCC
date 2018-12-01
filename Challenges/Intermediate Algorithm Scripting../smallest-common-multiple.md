https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/smallest-common-multiple/

## [MY SOLUTIONS]

```JS
function smallestCommons(arr) {
  //let arr = [1,5]
  let a = arr[0];
  let b = arr[1];

  if(a<b){
    // a = greatest Number and b= smallest Number
    [a,b] = [b,a] //Swapping        
  }
  
  
  var scm = a;  // let smallestCommonMultiplier is the greatest number 'a', every number is the scm of itself;
  var n1 = a;   // n1 = 5
  var n2 = a-1; // n2 = 4
  
  var i = a;
  while(i>b){
    if(n1 % n2 == 0){
      scm = n1;
      i--;
      n2--;
    }else{
      n1 += scm ; 
    } 
  }

  return scm;
}

smallestCommons([1,13]);
```

## [OTHERS]
```js
function smallestCommons(arr) {
  // Sort array from greater to lowest
  // This line of code was from Adam Doyle (http://github.com/Adoyle2014)
  arr.sort(function(a, b) {
    return b - a;
  });

  // Create new array and add all values from greater to smaller from the
  // original array.
  var newArr = [];
  for (var i = arr[0]; i >= arr[1]; i--) {
    newArr.push(i);
  }

  // Variables needed declared outside the loops.
  var quot = 0;
  var loop = 1;
  var n;

  // Run code while n is not the same as the array length.
  do {
    quot = newArr[0] * loop * newArr[1];
    for (n = 2; n < newArr.length; n++) {
      if (quot % newArr[n] !== 0) {
        break;
      }
    }

    loop++;
  } while (n !== newArr.length);

  return quot;
}

// test here
smallestCommons([1,5]);
```
