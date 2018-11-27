https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sum-all-primes

## [MY SOLUTIONS]
  
```js  
  function sumPrimes(num) {
  let primeArr = [];
  let check = false;
  for(var i=2; i<=num; i++){
    check = checkPrime(i);
    if(check){
      primeArr.push(i);
    }
  }
  
  return primeArr.reduce((acc,curr)=>{
    return acc+curr;
  })
  
}

function checkPrime(num){
  //num = Math.floor(num/2);
  for(var i=2; i<num; i++){
    if(num % i == 0){
      return false;
    }
  }
  return true;
}

sumPrimes(10);
```
## [OTHERS]
