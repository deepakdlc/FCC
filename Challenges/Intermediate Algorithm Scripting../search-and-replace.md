https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/search-and-replace/

## [My Solution]
```javascript
function myReplace(str, before, after) {
  var checkUpper = /[A-Z]/.test(before[0]);
  if(checkUpper)
    after = after[0].toUpperCase() + after.substr(1);
  else
    after = after[0].toLowerCase() + after.substr(1);  //else condition is not necessary
  return str.replace(before,after);
}

myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```

## [Other]

### Advance Solution

```javascript 
function myReplace(str, before, after) {

    // create a function that will change the casing of any number of letter in parameter "target"
    // matching parameter "source"
    function applyCasing(source, target) {
        // split the source and target strings to array of letters
        var targetArr = target.split("");
        var sourceArr = source.split("");
        // iterate through all the items of sourceArr and targetArr arrays till loop hits the end of shortest array
        for (var i = 0; i < Math.min(targetArr.length, sourceArr.length); i++){
            // find out the casing of every letter from sourceArr using regular expression
            // if sourceArr[i] is upper case then convert targetArr[i] to upper case
            if (/[A-Z]/.test(sourceArr[i])) {
                targetArr[i] = targetArr[i].toUpperCase();
            }
            // if sourceArr[i] is not upper case then convert targetArr[i] to lower case
            else targetArr[i] = targetArr[i].toLowerCase();
        }
        // join modified targetArr to string and return
        return (targetArr.join(""));
    }

    // replace "before" with "after" with "before"-casing
    return str.replace(before, applyCasing(before, after));
}

// test here
myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```

```js
// Add new method to the String object, not overriding it if one exists already
String.prototype.capitalize =  String.prototype.capitalize ||
    function() {
        return this[0].toUpperCase() + this.slice(1);
    };

const Util = (function () {
// Create utility module to hold helper functions
    function textCase(str, tCase) {
        // Depending if the tCase argument is passed we either set the case of the
        // given string or we get it.
        // Those functions can be expanded for other text cases.
        
        if(tCase) {
            return setCase(str, tCase);
        } else {
            return getCase(str);
        }

        function setCase(str, tCase) {
            switch(tCase) {
                case "uppercase": return str.toUpperCase();
                case "lowercase": return str.toLowerCase();
                case "capitalized": return str.capitalize();
                default: return str;
            }
        }

        function getCase(str) {
            if (str === str.toUpperCase()) { return "uppercase"; }
            if (str === str.toLowerCase()) { return "lowercase"; }
            if (str === str.capitalize()) { return "capitalized"; }
            return "normal";
        }
    }

    return {
        textCase
    };
})();

function myReplace(str, before, after) {
    const { textCase } = Util;
    const regex = new RegExp(before, 'gi');
    const replacingStr = textCase(after, textCase(before));

    return str.replace(regex, replacingStr);
}
```
