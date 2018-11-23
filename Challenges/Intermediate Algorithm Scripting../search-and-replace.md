https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/search-and-replace/

## [My Solution]
```javascript
function myReplace(str, before, after) {
  var i = str.indexOf(before);
  var checkUpper = /[A-Z]/.test(str[i]);
  if(checkUpper)
    after = after[0].toUpperCase() + after.substr(1);
  else
    after = after[0].toLowerCase() + after.substr(1);
  return str.replace(before,after);
}

myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```

## [Other]

