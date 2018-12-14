https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects/cash-register/

```js
function checkCashRegister(price, cash, cid) {
  var change = [];
  var amntDue = cash-price;
   
  var check = function (total){
    if(total>=amntDue) return true;
    else return false;
  }
  
  var coinValue = [0.01,0.05,0.1,0.25,1,5,10,20,100]
  var cid = cid.map(arr=>arr[1]);
  var total = cid.reduce((a,b)=>a+b);
  
  var i = 0;
  while(amntDue > coinValue[i]){
    i++;
  }
  
  for(var j=i-1; j>=0; j--){
    if(cid[j]>0 && amntDue>coinValue[j]){
      var need = Math.floor((amntDue/coinValue[j]))*coinValue[j];
      if(need <= cid[j]){
        change.push(need);
        amntDue = (amntDue-need).toFixed(2); 
        total -= need; 
      }else{
        change.push(cid[j]);
        amntDue = (amntDue-cid[j]).toFixed(2); 
        total -= cid[j]      
      }
    }
  }
  
  console.log(change);
  return change;
}

checkCashRegister(3.26, 100, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])
```
