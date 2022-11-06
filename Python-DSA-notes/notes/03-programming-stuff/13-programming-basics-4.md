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
                            // mask << 1 --> this means leftmost bit will be removed 
                                // & then on rightmost bit , 0 -> will be added
                            // mask | 1 -> means OR bitwise operator 
                                // so bit is 0 , then it'll become 1
                                // if bit is 1 , then it'll become 0 💡💡💡
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

        /* Another Solution
        class Solution {
            public : 
                int findComplement(int num) {
                    int mask = 0;

                    // creation of a mask
                    while(mask < num) {
                        // left shift 
                        mask = (mask << 1) ;
                        // OR bitwise operator with 1
                        mask = mask | 1;
                    }

                    int ans = (~num) & mask;
                    return ans;
                }
        } 
        */
        ```
        - `Advice to build logics` : 
            - then after writing logic , try to run this logic on different test case like on 3 , 5 & 10 , so on <br>
                in order to know whether our logic is working or not 
        - Note - `mask = (mask << 1) | 1;` ✅
            - `mask << 1` - this means leftmost bit will be removed & then on rightmost bit , 0 -> will be added
            - then `mask | 1` - means OR bitwise operator 
                - so bit is 0 , then it'll become 1
                - if bit is 1 , then it'll become 0 💡💡💡
            - `(~num) & mask` 
                - here `~num` means we converted that first 32 bits which are 0 into 1
                - then `& mask` means we converted `0 into 1` & `1 into 0` <br>
                    in order to convert that `111` by using `&` bitwise operator
    - explanation : thought process of code 
        ![dry run of above code](../../notes-pics/13-lecture/love-babbar/lecture-13-6.png)
        - let's see of `ans = (~5) & 7`
            ![dry run of above code](../../notes-pics/13-lecture/love-babbar/lecture-13-7.png)
        - why we didn't did this `while(mask <= num)` 
            - here why we didn't use `<=` because loop will run again & we'll get wrong output
            - so it's condition based on setbit of mask that we created <br>
            ![dry run of above code](../../notes-pics/13-lecture/love-babbar/lecture-13-8.png)
            - that's why we didn't put `<=` on condition & you can check via dry run
        - how do we able to know the logic ? 
            - at first time , we just know `~5` tilde will give the binary of 5 but first 32bits will be `1` <br>
            - so in right most bit , we want to get binary number ast it is from last set-bit which has 1 <br>
                & convert that first 32bits into 1 like this 
                ![how we think about the logic of this code](../../notes-pics/13-lecture/love-babbar/lecture-13-9.png)
            ![how we think about the logic of this code](../../notes-pics/13-lecture/love-babbar/lecture-13-10.png)
    - another solution we can do 
        - we can use counter like this 
            ```
            while (counter--) {
                mask <<
                something...
            }
            ```
        - to find the counter , next question we'll do based on counter

- leetcode Question : https://leetcode.com/problems/power-of-two/
