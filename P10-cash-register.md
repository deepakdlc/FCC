https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/cash-register/

```jsfunction checkCashRegister(price, cash, cid) {
  var change = [];
  var amntDue = (cash-price).toFixed(2);
   
  var check = function (total){
    if(total>=amntDue) return true;
    else return false;
  }
  
  var coinValue = [ 
    ["PENNY", 0.01],
    ["NICKEL", 0.05],
    ["DIME", 0.1],
    ["QUARTER", 0.25],
    ["ONE", 1],
    ["FIVE", 5],
    ["TEN", 10],
    ["TWENTY", 20],
    ["ONE HUNDRED", 100]
  ]

  var total = cid.map(arr=>arr[1]).reduce((a,b)=>a+b).toFixed(2);

  var i = 0;
  while(amntDue > coinValue[i][1]){
    i++;
  }

  console.log(i);
  for(var j=i-1; j>=0; j--){
    if(cid[j][1]>0 && amntDue>coinValue[j][1]){
      var need = Math.floor((amntDue/coinValue[j][1]))*coinValue[j][1];
      if(need <= cid[j][1]){
        change.push([cid[j][0],need]);
        amntDue = (amntDue-need).toFixed(2); 
        total -= need; 
      }else{
        change.push(cid[j]);
        amntDue = (amntDue-cid[j][1]).toFixed(2); 
        total -= cid[j][1];      
      }
    }
  }
  
  console.log(change);
  return change;
}

// Example cash-in-drawer array:
// [["PENNY", 1.01],
// ["NICKEL", 2.05],
// ["DIME", 3.1],
// ["QUARTER", 4.25],
// ["ONE", 90],
// ["FIVE", 55],
// ["TEN", 20],
// ["TWENTY", 60],
// ["ONE HUNDRED", 100]]

checkCashRegister(3.26, 100, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])
```
