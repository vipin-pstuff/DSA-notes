# Array problems - questions

## lecture 9 - love babbar (paid course) - Array problems + time + space complexity
  
- array homework questions
    ![array homework ques](../../notes-pics/15-2-lecture/love-babbar/lecture-15-2-0.png)
    - `find subarrays with equal 0s and 1s` -> this question is difficult one , <br>
        but before doing this question , first we need to do question i.e largest sub-array with equal 0s and 1s 
    - inside `find sub-array with 0 sum in an array` question
        - understanding 
            - situation when we if have `0` at starting index 
                - an array contain negative or positive numbers or both like this `[2, -3, 1, 4, 5]`
                - if we find the `prefix sum` , so to get the `prefix sum` these are the steps 
                    - like this first element comes as it is in 0 index 
                    - if we do 2 + (-3) = -1 , so we'll get `[2, -1]` 
                    - now if we add 2 + (-3) + 1 = 2 + (-2) , then we'll get 0 , so `[2, -1, 0]`
                    - again, we take elements from input array like this 2 + (-3) + 1 + 4 , so we'll get 4 , so `[2, -1, 0, 4]`
                    - & now , we'll take elements from input array i.e 2 + (-3) + 1 + 4 + 5 , so we'll get `[2, -1, 0, 4, 9]`
                - now we got the prefix sum i.e `[2, -1, 0, 4, 9]` , <br>
                    so now we can see , here we got the `0` , so when we did sum from 2 to 0 i.e 2 , -1 & 0 , <br>
                    which means we're getting `0` , so we'll print this much array elements i.e `[2, -1, 0]`
                - conclusion : this question is based on prefix sum <br>
                - what is `prefix` means ? 
                    - Eg : let's say you have a string "find"  
                    - so prefix will be `f` - this is 1st prefix , `fi` - 2nd prefix , `fin` - 3rd prefix & so on... 
            - let's understand when we have `0` in the middle
                - Eg : `[2, 3, 0, -3, 5]`
                - so here you can see that part of input array i.e `[3, 0, -3]` is creating `0` sub-array
                - so prefix sum of that input array will be like this `[2, 5, 0, 2, 7]` <br>
                    here we can see that there's one number is repeating i.e `2` 
                - so when any number is repeating 2 times then means middle elements is giving 0 sum i.e `[2, 5, 0, 2]`
            - conclusion : there are 2 cases
                - if you get the `0` then that index block (which has `0`) is the 0 sum <br>
                    or if any number is repeating 2 times , then middle of them is the `0` sub-array sum
                - so complete logic is dependent on prefix sum
    - `Ques` : find factorial of a large number
        - understanding 
            - 


