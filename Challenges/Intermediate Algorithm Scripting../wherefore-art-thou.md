https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/wherefore-art-thou/

## [My Solutions]

#### [1]
```js
function whatIsInAName(collection, source) {
  // What's in a name?
  var arr = [];
  var check;
  // Only change code below this line
  for(var obj of collection){
    check = true;
    for(var prop in source){
      if(obj.hasOwnProperty(prop)){
        if(obj[prop]==source[prop])
          continue;
      }
      check = false;
    }
    if(check){
      arr.push(obj);
    }
  }
  
  // Only change code above this line
  return arr;
}
```
#### [2]
```js
function whatIsInAName(collection, source) {
  // What's in a name?
  var arr = [];
  let check = null;
  // Only change code below this line
  return Object.keys(source);
  arr =  collection.filter(obj =>{
    return keys.every(prop=> obj.hasOwnProperty(prop) && obj[prop] == source[prop])
  });
  // Only change code above this line;
}

whatIsInAName([{ "apple": 1, "bat": 2 }, { "bat": 2 }, { "apple": 1, "bat": 2, "cookie": 2 }], { "apple": 1, "bat": 2 });

## [OTHERS]

```JS
function whatIsInAName(collection, source) {
  // "What's in a name? that which we call a rose
  // By any other name would smell as sweet.”
  // -- by William Shakespeare, Romeo and Juliet
  var srcKeys = Object.keys(source);

  // filter the collection
  return collection.filter(function (obj) {
    return srcKeys
      .map(function(key) {
        return obj.hasOwnProperty(key) && obj[key] === source[key];
      })
      .reduce(function(a, b) {
        return a && b;
      });
  });
}

// test here
whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```
```
