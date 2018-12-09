https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/roman-numeral-converter

## [MY SOLUTIONS]


```JS
function convertToRoman(num) {
    let numToRoman = {
        0 : '', //in case num%10 == 0 
        1 : 'I',
        2 : 'II',
        3 : 'III',
        4 : 'IV',
        5 : 'V',
        6 : 'VI',
        7 : 'VII',
        8 : 'VIII',
        9 : 'IX',
        10 : 'X',
        20 : 'XX',
        30 : 'XXX',
        40 : 'XL',
        50 : 'L',
        60 : 'LX',
        70 : 'LXX',
        80 : 'LXXX',
        90 : 'XC',
        100 : 'C',
        200 : 'CC',
        300 : 'CCC',
        400 : 'CD',
        500 : 'D',
        600 : 'DC',
        700 : 'DCC',
        800 : 'DCCC',
        900 : 'CM',
        1000 : 'M',
        2000 : 'MM',
        3000 : 'MMM'
    }

    let numSplit = function(num){
        let arr = [];
        let rev = 0, len = 0 , pv = 0;
        while(num!=0){
            rev = rev*10 + num%10;
            pv = num%10 * Math.pow(10,len);
            num = Math.floor(num/10);
            len++;
            arr.unshift(pv);
        }
        return arr;
    }

    let romanNum = ''; 
    numSplit(num).forEach(digit => {
    romanNum += numToRoman[digit];
    });

    return romanNum;
}

convertToRoman(501); 
```

### [OTHERS SOLUTIONS]

