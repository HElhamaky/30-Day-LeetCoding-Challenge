#### So, how do we write code that returns true if a number ’n’ is happy?

Using the example above, we would follow these steps:

1. break the number 19 into separate digits of 1 and 9.
2. square each digit
3. sum the squares
4. check if the sum equals 1
5. if the sum is 1, return true
6. otherwise, go back to step 1 and repeat.

#### Steps 1 & 2: Break the number into digits and square each digit

```javascript
var arr = num.toString(10).replace(/\D/g, '0').split('').map(Number);
```
Let’s say n is 19. Here’s how the code above works, step by step:


#### Step 3: Sum the squares
Iterate over array elements, get the square of each element then get the sum of these squares.

```javascript
    var x = 0 ;
    for(i=0 ; i<= arr.length-1 ; i++){    
        //x = x + arr[i];
        x = x + Math.pow(arr[i], 2);
    }

    num = x;
```

#### Steps 4 & 5: Check the sum: return true if it equals one.
```javascript
    if (num == 1){
        return true;
    }else{
        return false;
    };
```

#### Step 6, the hard part: How exactly do you start over?
I wanted to code a recursive solution, like this.

```javascript
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
```

But if sum never equals one, the function will continue in an infinite loop. Noooooo !

To stop this from happening, we need a base case. In other words, when do we want this function to stop calling itself?

If a number is happy, sum eventually resolves to 1. But if it is not happy, I’m not sure what happens (I don’t know that much about number theory). So I decided the function should call itself a finite amount of times.

To make this happen, I wanted to add a counter.
That’s hard to do in a recursive function. I’m used to setting an initial value for a counter near the top of the function, i.e.: let counter = 0. But if you do that in a recursive function, your counter is reset to zero with each recursion.

To get around this, you can pass the counter into your function as an argument with a default value of zero.

If counter is passed in with a value, the function will use that value; but if counter is passed in with no value, the function will read counter as 0.

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

Let’s unpack that.

We are going to return ‘result’ at the end of our function. We give result an initial value of false.

Then, starting on line 5, as long as we have tried fewer than 8 times, we break n into its digits, square them, sum the squares, and check to see if the sum is 1. If it is, we set result equal to true and break out of the loop. Otherwise, we increment our counter and start over.

Note: first I tried 5 as the maximum number of loops; it didn’t pass LeetCode tests, so I upped the number to 8, which did work.

And, it worked well!

Reference :- 
[Algorithms 101: Happy Number in JavaScript](https://medium.com/javascript-in-plain-english/algorithms-101-happy-number-in-javascript-bddeb3d17035)