# Programming Basics 4 

## lecture 5 - love babbar (paid course)

- leetcode question : https://leetcode.com/problems/number-complement/
    - so in this question , we need to get the complement like this 
        ![number complement](../../notes-pics/13-lecture/love-babbar/lecture-13-0.png)
    - Eg : input is 1 & binary representation is 1 , so complement will be 0
    - now we don't need to worry about code , we understand the question Yes or NO
    - Examples : 
        - let's say you have input as `6` , binary representation of it is `110` , complement of binary `6` is `001` <br>
            & then complement of `6^1` is `001` now decimal representation of `001` is `1`
        - Eg : input is `3` , binary representation is `11` , complement of `3^1` is `00` now decimal representation is `0`
        ![number complement](../../notes-pics/13-lecture/love-babbar/lecture-13-1.png)
    - brainstorming : 
        ![what can goes wrong](../../notes-pics/13-lecture/love-babbar/lecture-13-2.png)
        - so we're able to get the complement of a number via `~` tilde sign <br>
            but how we can convert that first 32 bits from 1 into `0` 💡💡💡
        - so we can do mask like this <br>
            ![what can goes wrong](../../notes-pics/13-lecture/love-babbar/lecture-13-3.png)
        - output 
            ![converting into correct binary representation](../../notes-pics/13-lecture/love-babbar/lecture-13-4.png)
        - so we're flip all the bits via `~` tilde sign & then we're using `&` with a mask. so we need to prepare the mask <br>
            so how we can create a mask ? 
            ![creating a mask](../../notes-pics/13-lecture/love-babbar/lecture-13-5.png)
    - code 
        ```cpp
        class Solution {
            public : 
                int findComplement(int num) {
                    int mask = 0; // by-default , at starting mask will be 0

                    // mask < num , means we want to add 1 inside the mask until mask is less than number
                    while(mask < num) {
                        // here in order to add 1 inside the mask 
                            // first : we need to shift 1bit via left shift bitwise operator
                            // second : then add 1 via OR bitwise operator
                        mask = (mask << 1) | 1;
                    }

                    // now to get the answer , we used tilde sign -> ~ means flip all the bits 
                        // but we don't want to flip the bits of last setbit that's why we created mask 💡💡💡
                        // then we add the mask at last after total 32 bits via AND bitwise operator -> & 
                    int ans = (~num) & mask;
                    return ans;
                }
        } 
        // input : 10
        // output : 5
        ```
        - `Advice to build logics` : 
            - then after writing logic , try to run this logic on different test case like on 3 , 5 & 10 , so on <br>
                in order to know whether our logic is working or not 
    - thought process of code 

        timeline : 16:04

