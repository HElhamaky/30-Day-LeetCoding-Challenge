### ALGORITHM
1.Have a global variable currentSum;

2.Have a global variable max that will also be the return value;

3.Loop through the array, check if the current element **(nums[i])** is greater than the current sum and current element put together **(i.e currentSum + nums[i])**;

4.if it is greater, reassign the currentSum variable to be the current element, **nums[i]**;

5.if it is not, reassign the currentSum variable to be the summation of both the existing current sum and the current array element **(currentSum = currentSum + nums[i])**

6.finally, check if the **currentSum** is greater than the current maximum. if it is, reassign the current max to be equal to currentSum.

7.Then return **max**.

### CODE

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    
    let currentSum = nums[0];
    let maxSum = nums[0];
    
    for(let i = 1 ; i < nums.length ; i++){
        if(nums[i] > (currentSum + nums[i])){
            currentSum = nums[i];
        }else{
            currentSum = currentSum + nums[i];
        }
        
        if(currentSum > maxSum){
            maxSum = currentSum;
        }
    }
        
    return maxSum;
};
```