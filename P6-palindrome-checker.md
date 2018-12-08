https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/palindrome-checker

## [MY SOLTIONS]
```JS
function palindrome(str) {
  // Good luck!
  str = str.toLowerCase().split(/[^\w]|[_]/).join("");
  var revStr = str.split("").reverse().join("");
  return str === revStr;
}
palindrome("0_0 (: /-\ :) 0-0");
```

## [OTHERS SOLUTION]
