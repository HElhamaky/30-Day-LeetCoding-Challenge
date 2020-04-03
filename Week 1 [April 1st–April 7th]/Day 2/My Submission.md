```javascript
/**
 * @param {number} n
 * @return {boolean}
 */

var isHappy = function(num) {
    
var counter = 0;
while(num != 1 && counter < 8 ){
    var arr = num.toString(10).replace(/\D/g, '0').split('').map(Number);
    var x = 0 ;
    for(i=0 ; i<= arr.length-1 ; i++){    
    //x = x + arr[i];
    x = x + Math.pow(arr[i], 2);
    }

    num = x;
    counter++;
}
    
    console.log(num);
    if (num == 1){
        return true;
    }else{
        return false;
    };
    
};
```