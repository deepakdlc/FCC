https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/everything-be-true/

## [MY SOLUTION]
```JS
function truthCheck(collection, pre) {
  // Is everyone being true?
  return collection.every(item=>item.hasOwnProperty(pre) && item[pre]);
}

truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex");
```

## [OTHERS]
