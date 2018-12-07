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
