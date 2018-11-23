https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/dna-pairing

## [My Solution]

```js
  
  function pairElement(str) {
  var arr = [];
  for(var char of str){
    if(char === 'A')
      arr.push(['A','T']);
    else if(char === 'T')
      arr.push(['T','A']);
    else if(char === 'G')
      arr.push(['G','C']);
    else
      arr.push(['C','G']);
  }
  return arr;
}

pairElement("GCG");

```
