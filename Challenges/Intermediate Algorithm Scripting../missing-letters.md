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

## [OTHERS]

### Simplified Advanced
function fearNotLetter(str) {
  for (let i = 1; i < str.length; ++i) {
    if (str.charCodeAt(i) - str.charCodeAt(i-1) > 1) {
      return String.fromCharCode(str.charCodeAt(i - 1) + 1);
    }
  }
}

### Advanced
function fearNotLetter(str) {
  var allChars = '';
  var notChars = new RegExp('[^'+str+']','g');

  for (var i = 0; allChars[allChars.length-1] !== str[str.length-1] ; i++)
    allChars += String.fromCharCode(str[0].charCodeAt(0) + i);

  return allChars.match(notChars) ? allChars.match(notChars).join('') : undefined;
}

// test here
fearNotLetter("abce");
