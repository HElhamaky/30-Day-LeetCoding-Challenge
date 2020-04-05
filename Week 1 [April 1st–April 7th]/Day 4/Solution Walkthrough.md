### Move all zeroes to end of array
Given an array of random numbers, Push all the zero’s of a given array to the end of the array. 

*For example*, if the given arrays is **{1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0}**, it should be changed to **{1, 9, 8, 4, 2, 7, 6, 0, 0, 0, 0}**. The order of all other elements should be same. Expected time complexity is O(n) and extra space is **O(1)**.

#### Example:

        Input :  arr[ ] = {1, 2, 0, 4, 3, 0, 5, 0};

        Output : arr[ ] = {1, 2, 4, 3, 5, 0, 0, 0};
        
        ---------------------------------------
        
        Input : arr[ ]  = {1, 2, 0, 0, 0, 3, 6};

        Output : arr[ ] = {1, 2, 3, 6, 0, 0, 0};

#### Note :- 
1. You must do this in-place without making a copy of the array.
2. Minimize the total number of operations.

#### Solution :-
1. There can be many ways to solve this problem. Following is a simple and interesting way to solve this problem.

2. Traverse the given array ‘nums’ from left to right. While traversing, maintain **count of non-zero** elements in array. 

3. Let the count be **‘count’**. For every non-zero element **nums[i]**, put the element at **‘nums[count]***’ and increment **‘count’**. 

4. After complete traversal, *all non-zero elements have already been shifted to front end* and **‘count’** is set as *index of first 0*. 

5. Now all we need to do is that run a loop which *makes all elements zero from ‘count’ till end of the array*.

