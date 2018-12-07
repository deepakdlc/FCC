https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/map-the-debris/

##[MY SOLUTION]

```JS
function orbitalPeriod(arr) {
  var GM = 398600.4418;
  var earthRadius = 6367.4447;
  
  return arr.map(obj=>{
    var semiMajorAxis = earthRadius + obj.avgAlt;

    var time = Math.round(2*Math.PI*Math.sqrt(Math.pow(semiMajorAxis,3)/GM));

    return {name: obj.name, orbitalPeriod: time}
  })
}
orbitalPeriod([{name : "sputnik", avgAlt : 35873.5553}]);
```

## [OTHERS SOLUTIONS]

### Advance

```JS
function orbitalPeriod(arr) {
  var GM = 398600.4418;
  var earthRadius = 6367.4447;

  // Loop through each item in the array arr
  arr.forEach(function(item) {
    // Calculate the Orbital period value
    var tmp = Math.round(2 * Math.PI * Math.sqrt(Math.pow(earthRadius + item.avgAlt, 3) / GM));
    //Delete the avgAlt property
    delete item.avgAlt;
    //Add orbitalPeriod property
    item.orbitalPeriod = tmp;
  });
  return arr;
}

// test here
orbitalPeriod([{name : "sputnik", avgAlt : 35873.5553}]);
```
