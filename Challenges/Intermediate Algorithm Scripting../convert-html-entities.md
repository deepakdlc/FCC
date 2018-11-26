https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/convert-html-entities/

## [My Solutions]

function convertHTML(str) {
  // &colon;&rpar;
  let charToHTML = {
    '&': '&amp;',
    '<': '&lt;',
    '>': '&gt;',
    '\"' : '&quot;',
    '\'' : '&apos;',
    '\w' : '\w',
    'abc' : 'abc'
  }
  var arr = str.match(/&|>|<|"|'|abc/g);
  for(var char of arr){
   str = str.replace(char,charToHTML[char]);
  }
  return str;
}

convertHTML("Dolce & Gabbana");
