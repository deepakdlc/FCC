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


### [Other]
## Advance

```js
    function pairElement(str) {
    //create object for pair lookup
    var pairs = {
      "A": "T",
      "T": "A",
      "C": "G",
      "G": "C"
    }
    //split string into array of characters
    var arr = str.split("");
    //map character to array of character and matching pair
    return arr.map(x => [x,pairs[x]]);
  }

  //test here
  pairElement("GCG");

```
