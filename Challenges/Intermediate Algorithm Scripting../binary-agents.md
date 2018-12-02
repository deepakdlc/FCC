https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/binary-agents

## [MY SOLUTIONS]

```JS
function binaryAgent(str) {
  var strArr = str.split(' ');
  var binToStr = [];
  
  for(var item of strArr)
    binToStr.push(String.fromCharCode(parseInt(item,2)));
  
  return binToStr.join('');
}
```
