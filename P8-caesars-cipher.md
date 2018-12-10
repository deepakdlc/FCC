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
function rot13(str) { // LBH QVQ VG!
  return str.replace(/[A-Z]/g, L => String.fromCharCode((L.charCodeAt(0) % 26) + 65));
}
```


### Intermediate

```js
    // Solution with Regular expression and Array of ASCII character codes
    function rot13(str) {
      var rotCharArray = [];
      var regEx = /[A-Z]/ ;
      str = str.split("");
      for (var x in str) {
        if (regEx.test(str[x])) {
          // A more general approach
          // possible because of modular arithmetic
          // and cyclic nature of rot13 transform
          rotCharArray.push((str[x].charCodeAt() - 65 + 13) % 26 + 65);
        } else {
          rotCharArray.push(str[x].charCodeAt());
        }
      }
      str = String.fromCharCode.apply(String, rotCharArray);
      return str;
    }

    // Change the inputs below to test
    rot13("LBH QVQ VG!");
```

### Basic
```js
    function rot13(str) {
      // Split str into a character array
      return str.split('')
      // Iterate over each character in the array
        .map.call(str, function(char) {
          // Convert char to a character code
          x = char.charCodeAt(0);
          // Checks if character lies between A-Z
          if (x < 65 || x > 90) {
            return String.fromCharCode(x);  // Return un-converted character
          }
          //N = ASCII 78, if the character code is less than 78, shift forward 13 places
          else if (x < 78) {
            return String.fromCharCode(x + 13);
          }
          // Otherwise shift the character 13 places backward
          return String.fromCharCode(x - 13);
        }).join('');  // Rejoin the array into a string
    }
```
