https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/missing-letters/

##  [MY SOLUTION]

```js
function fearNotLetter(str) {
  var ascii = str.charCodeAt(0);

  for(var char of str){
    if(char.charCodeAt() != ascii){
      return String.fromCharCode(ascii);
    }
    ascii++;
  }      
  return undefined;
}

fearNotLetter("abce");
```
