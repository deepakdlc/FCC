https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/telephone-number-validator

## [MY SOLUTION]

```JS
function telephoneCheck(str) {
  // Good luck!
  var check = /(^1\s?)|(\d{3}|\(\d{3}\))([\s-]?)\d{3}\3?\d{4}$/.test(str)
  console.log(check);
  return check;
}

telephoneCheck("555-555-5555");
```
