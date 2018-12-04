https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/arguments-optional/

## [MY SOLUTIONS]

```JS
function addTogether(a,b){
  if(arguments.length == 2 && check(...arguments)){
    return a+b;
  }
  else if(check(...arguments)){
    return function(b){
      if(check(...arguments))
        return a+b;
    }
  }
}

var check = function(...arg){
  for(var i=0; i<arguments.length; i++){
    if(typeof arguments[i]!="number"){
      return false;
    }
  }
  return true;
} 
```

## [OTHERS]

### Advance
```js
 function addTogether() {
      var args = Array.from(arguments);
      return args.some(n => typeof n !== 'number') ? 
        undefined: 
        args.length > 1 ?
          args.reduce((acc, n) => acc += n, 0):
          (n) => typeof n === "number" ? 
            n + args[0]:
            undefined;
    }

    // test here
    addTogether(2,3);
```

### Intermediate
```js
function addTogether() {
      var args = new Array(arguments.length);
      //Storing the arguments in an array
      for(var i = 0; i < args.length; ++i) {
          args[i] = arguments[i];
        }
     //Check for the arguments length
     if(args.length == 2){
        //If there are two arguments,check for the type of both arguments
        //Use typeof to check the type of the argument(both should be numbers)
        if(typeof args[0] !== 'number' || typeof args[1] !=='number' ){
          return undefined;
          }
        return args[0]+args[1];
       }
     //When only one argument is provided
     if(args.length == 1){
         a= args[0];
         //Check the  argument using typeof 
        if(typeof a!=='number'){
            return undefined;
          }
        else{
           //Making use of closures 
           return function(b){
           //Checking the second argument 
             if(typeof b !=='number'){
               return undefined;
               }
             else
               return a+b;
              };
          }
        }
    }
```

### Basic
```js
function addTogether() {
      // Function to check if a number is actually a number
      // and return undefined otherwise.
      var checkNum = function(num) {
        if (typeof num !== 'number') {
          return undefined;
        } else
          return num;
      };

      // Check if we have two parameters, check if they are numbers
      // handle the case where one is not
      // returns the addition.
      if (arguments.length > 1) {
        var a = checkNum(arguments[0]);
        var b = checkNum(arguments[1]);
        if (a === undefined || b === undefined) {
          return undefined;
        } else {
          return a + b;
        }
      } else {
        // If only one parameter was found, returns a new function that expects two
        // Store first argument before entering the new function scope
        var c = arguments[0];

        // Check the number again, must be outside the function to about returning an object
        // instead of undefined.
        if (checkNum(c)) {
          // Return function that expect a second argument.
          return function(arg2) {
            // Check for non-numbers
            if (c === undefined || checkNum(arg2) === undefined) {
              return undefined;
            } else {
              // if numbers then add them.
              return c + arg2;
            }
          };
        }
      }
    }
```
