

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {

    var dubl = [];
    var srtnum = nums.sort(function(a, b){return a - b});
    
    for( let i = 1 ; i<= srtnum.length ; i++){
    if(srtnum[i] == srtnum[i-1]){
        dubl.push(srtnum[i]);
        }
    };
    
    function onlyUnique(value, index, self) { 
        return self.indexOf(value) === index;
    }

    var unique = nums.filter( onlyUnique );
    
    
    var difference = unique.filter(x => !dubl.includes(x));
    
    return difference;
    
};
```