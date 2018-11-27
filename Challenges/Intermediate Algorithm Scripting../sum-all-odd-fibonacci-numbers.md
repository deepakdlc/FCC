https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-odd-fibonacci-numbers/

## [MY SOLUTIONS]

```js
function sumFibs(num) {
  var a=1, b=1, OddSum=2, nxt=a+b;

  for(var i=0; nxt<=num; i++){
    if(nxt%2 != 0){
      OddSum+= nxt;
    }
    a=b;
    b=nxt;
    nxt=a+b;
  }
  
  return OddSum;
}

sumFibs(4);
```

## [OTHERS]

### Basic
```js
function sumFibs(num) {
    var prevNumber = 0;
    var currNumber = 1;
    var result = 0;
    while (currNumber <= num) {
        if (currNumber % 2 !== 0) {
            result += currNumber;
        }

        currNumber += prevNumber;
        prevNumber = currNumber - prevNumber;
    }

    return result;
}
```

### Intermediate
```js
function sumFibs(num) {
    // Perform checks for the validity of the input
    if (num < 0) return -1;
    if (num === 0 || num === 1) return 1;

    // Create an array of fib numbers till num
    const arrFib = [1, 1];
    let nextFib = 0;
    
    // We put the new Fibonacci numbers to the front so we
    // don't need to calculate the length of the array on each
    // iteration
    while((nextFib = arrFib[0] + arrFib[1]) <= num) {
        arrFib.unshift(nextFib);
    }

    // Sum only the odd numbers and return the value
    return arrFib.reduce((acc, curr) => {
        return acc + curr * (curr % 2);
    });
}
```
