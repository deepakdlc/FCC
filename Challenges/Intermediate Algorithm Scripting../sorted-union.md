https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sorted-union/

## [My Solution]

```js
function uniteUnique(arr) {
  for(var i=1; i<arguments.length; i++){
    arguments[i].forEach(item=>{
      if(!arr.includes(item)){
        arr.push(item);
      }
    })
  }
  return arr;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```
