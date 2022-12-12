# binary search problems 

## lecture - love babbar (paid course)

- here we'll see how to reduce the search space , so in this , if we do only 1 ques <br>
    then same strategy will be applied on every questions to write code & make approach 💡💡💡

- till yet , we did questions of binary search i.e classical ques , 2D array <br>
    & we need to do `search space reduction` ques

- eg : of search space reduction questions (which are based on binary search algo) are 
    - `1` : book allocation problem (which is already done on YT)
    - `2` : find square root via BS
    - `3` : aggressive cows
    - `4` : painter partition
    - `5` : EKO spoj
    - `6` : roti prata

- ques : EKO SPOJ
    - https://www.spoj.com/problems/EKO/
        - we'll do this question only then the same technique will be applied on these other questions
        - story questions are like this question  
    - understand 
        ![understanding the question](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-0.png) <br>
            means that person will set a particular height & cut all the trees for woods
        - questions is saying that 
            - tell the max height when that person start cutting all the trees <br>
                then that person at-least can cut `m meter` of wood 
            - means that person wants to cut all those trees for `m meter` <br>
                & that `m meter` let's say 50m which is given as input <br> 
            - so ramesh will set a height to cut all those tress on same height ,<br>  
                so questions is asking that tell the max height through which when ramesh cut all those trees <br>
                then answer at-least reach at m meter means `>= m` 💡💡💡
        - doubt : what if height of a tree is less than the height (which set for cutting all those trees) <br> 
            so answer will be `0` 
    - approach
        - `1st approach` : brute force (means doing hardwork & code not optimize)
            ![brute force approach](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-1.png) <br>
        - `2nd approach` : using binary search algo (optimizing the solution)
            ![what is TLE & how to avoid it , what is constraints](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-2.png) 
            ![approach STEP 1](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-3.png) 
            ![approach STEP 2](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-4.png) <br>
            so can we write the code like this 
            ```
            s = 0 , e = Max(arr)
            while(s <= e) {
                int mid = (s+e)/2;
                if (isPossibleSolution(mid)) {
                    ans = mid ; ---> here storing the answer
                    s = mid + 1 ; ---> for right side means going up
                } else {
                    // left means going down
                    e = mid - 1;
                }
            }

            bool isPossibleSolution(int mid, int arr[], int target) {}
            ```
            - DRY RUN with example & understanding going right & left 💡💡💡
                ![DRY RUN with example & what is means by going right & left side](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-5.png) 
                - checking mid value whether it's a possible answer or not
                    ![DRY RUN for isPossibleSolution() function](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-6.png) 
                - basically , the game is all about right & left 
                - & most of the time `isPossibleSolution()` function is solved via brute force solution <br>
                    but if you want to optimize this also , then you can do 💡💡💡
                - if you have confusion in left & right then see this 💡
                    ![confusion in right & left approach](../../notes-pics/16-3-lecture/love-babbar/lecture-16-3-7.png) 
            - working only on isPossibleSolution() function
                ```
                bool isPossibleSolution(int mid, int arr[], int target) {
                    sum = 0 ; --> this variable will calculate the sum
                    for (i -> 0 -> < n) {
                        int difference = 0;
                        if (arr[i] > mid) ---> means if the size of a tree is bigger than the size of our cutter machine
                                                then we'll find the difference means do subtraction 💡💡💡 
                            difference = arr[i] - mid ;
                        sum = sum + difference ;
                    }

                    -- here we're doing comparison
                    if (sum >= target)
                        return true
                    else 
                        return false
                }
                ```


- advice 👍
    - do DRY RUN on pen & paper to understand that problem clearly 
            
