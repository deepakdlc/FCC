https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/pig-latin/

## [My Solution]
### [1]
```javascript
function translatePigLatin(str) {
  let check = /^[aeiou]/.test(str);

  if(check){
    return str+"way";
  }
  else if(/\b[^aeiou]+\b/.test(str)){
    return str+"ay";
  }
  else{
    return str.replace(/(^[^aeiou]+)(\w+)/,'$2$1ay')
  }  
}

translatePigLatin("consonant");
```
### [2]
```js
function translatePigLatin(str) {
  let consonant = str.match(/^[^aeiou]+/);
  return Boolean(consonant) ? str.slice(consonant[0].length,) + consonant[0] + "ay" : str + "way";
}

translatePigLatin("glove");
```
## [Others]

### Basic

```javascript
function translatePigLatin(str) {
  // Create variables to be used
  var pigLatin = '';
  var regex = /[aeiou]/gi;

  // Check if the first character is a vowel
  if (str[0].match(regex)) {
    pigLatin = str + 'way';

  } else if(str.match(regex) === null) {
    // Check if the string contains only consonants
    pigLatin = str + 'ay';
  } else {

    // Find how many consonants before the first vowel.
    var vowelIndice = str.indexOf(str.match(regex)[0]);

    // Take the string from the first vowel to the last char
    // then add the consonants that were previously omitted and add the ending.
    pigLatin = str.substr(vowelIndice) + str.substr(0, vowelIndice) + 'ay';
  }

  return pigLatin;
}

// test here
translatePigLatin("consonant");
```

### Advance
```javascript
function translatePigLatin(str) {
    var strArr = [];
    var tmpChar;

    // check if the char is consonant using RegEx
    function isConsonant(char) {
        return !/[aeiou]/.test(char);
    }

    // return initial str + "way" if it starts with vowel
    // if not - convert str to array
    if (!isConsonant(str.charAt(0)))
        return str + "way";
    else
        strArr = str.split("");

    // push all consonats to the end of the array
    while (isConsonant(strArr[0])) {
        tmpChar = strArr.shift();
        strArr.push(tmpChar);
    }
 // convert array to string and concatenate "ay" at the end
 return strArr.join("")+"ay";
}
```
