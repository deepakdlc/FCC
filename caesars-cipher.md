https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/caesars-cipher/

## [MY SOLUTIONS]

```JS
function rot13(str) { // LBH QVQ VG!
  let decodedStr = ''
  
  for(var char of str){
    if(char >='A' && char <= 'Z'){
      if(char <= 'M'){
        decodedStr += String.fromCharCode(char.charCodeAt() + 13);
        continue;
      }
        decodedStr += String.fromCharCode(char.charCodeAt()+13-26);
      continue;
    }
    decodedStr += char;
  }
  return decodedStr;
}

// Change the inputs below to test
rot13("LBH QVQ VG!");
```

## [OTHERS]

### Advance

```js

```


### Advance

```js

```
