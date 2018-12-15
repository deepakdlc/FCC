https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/cash-register/

```js
function checkCashRegister(price, cash, cid) {
  var change = [];
  var amntDue = (cash-price);
   
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

  var total = cid.map(arr=>arr[1]).reduce((a,b)=>a+b);
  if(amntDue == total){
    return {status: "CLOSED", change: cid};
  }
  else if(amntDue>total){
    return  {status: "INSUFFICIENT_FUNDS", change: []};
  }
  var i = 0;
  while(amntDue > coinValue[i][1]){
    i++;
  }

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
  
  if(amntDue!=0){
    return{status: "INSUFFICIENT_FUNDS", change: []}
  }
  else;
    return {status: "OPEN", change: change};
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

checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]);
```
