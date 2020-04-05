```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
     let n = nums.length;
    let count = 0;
    for(let i = 0 ; i< n ; i++){
        if(nums[i] != 0){
            nums[count] = nums[i];
            count++;
        }
    }
    
    while (count < n){
        nums[count] = 0;
        count++;
    }
    
    console.log(nums);
    return(nums);
};
```