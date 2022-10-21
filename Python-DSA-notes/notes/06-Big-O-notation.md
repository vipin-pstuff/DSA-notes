# Big O Notation : Time & Space Complexity

## lecture - abdul bari sir

- time complexity : in daily life when we do any work/task , we want to know how much time it takes for that performing that particular task
    - so usually , in daily life , we measure the time based on the work that we have to do
    - so now we're using machines to do over work that's computers to do over work <br>
        so we want to know how much machine takes for doing the same task
    - Eg : like if a person is making a bread in 15 min - 20min then
        - if you're using machine for making that bread then how much the machine takes 
        - so if machine is taking 4-5hrs then it's better to do it manually
    - so how much time a machine takes to complete that task is very important for us <br>
        so we use machine for problem solving & what type of problem solving <br>
        `what type of problem solving` : the work that we use do it using pen & paper , so that same work <br>
        we want our computers to do that . so computers are used for performing computation task <br>
        so computation also needs time . that's why we want to measure how much time a machine will take
    - so actually , that depends on the process or the procedure for completing that task <br>
        so that time complexity basically depends on the procedure that you're adopting 💡💡💡
    - so we'll see examples & based on these examples , we'll see what procedure may take what amount of time 💡💡💡

    - Eg : of array `[2,5,9,6,12,15,8,3,7]` & there's are 10 elements
        - now tell me that , inside this array , will always be 10 elements or depends on the problem ? <br> 
            so it's depends on the problem
        - so how many elements will be there ? , so we say `n` elements will be there <br> 
            it maybe 10 or 10,000 or 10 million , so we don't know how many elements are there that's why we say `n` elements 
        - so that number of elements may start from 1 to infinity , so we don't define infinity for the maximum number <br>
            or whatever that number you can imagine you take , so here `n` means not just 5 or 10 <br>
            so `n` means some number of elements
        - so let's say there're `n` elements inside that array like this
            ![n elements inside the array](../notes-pics/06-lecture/abdul-bari/lecture-6-0.png)
            - now what operation you want to do with these elements , so we want to add all of them
            - so for adding then we need to go through all of them , so you need to take one by one & adding them
            - so how much time this adding operation will takes , so time depends on the number of elements <br> 
                so here `what's the time taken` i.e n 
            - so now next thing we want to do i.e i want to search for a particular number <br>
                like whether element 12 is there or not . or let's say i want to search for element 21 <br>
                so we need to check for all & there's no 21 element
            - so how much time it's taking . so it depends on the number of elements that you have to compare
            - so how many elements are there . so `n` elements are there , so what's the time taken i.e `n` <br>
                which means when we have `n` elements in an array & you're going through all of them just once or one time <br>
                then the time is `n`
            - so `n` is represented as a degree , but ususally , we use the term i.e order means `order of n` like this 
                ![O(n)](../notes-pics/06-lecture/abdul-bari/lecture-6-1.png)
            - & there're other terms like BigO , Omega , theta , we'll see at the end of the course of abdul bari <br>
                because we'll having the good understanding of time complexity & these other terms are Asymptotic notations
        - `2 thing` : if we want to access all the elements then what the code we have to write , so we have to write this 
            ```js
            for (let i = 0 ; i < n ; i++) {
                /* 
                    here whatever you want to do like count number of elements , sum of elements of an array , etc
                    that logic we'll write here
                 */
            }
            ```
            - so this for loop will take each element one by one , so time will be O(n) mneas order of n
            - now for finding the time complexity either we can measure the time based on the work that we're doing <br>
                means what's your procedure , if you're clear with your procedure then you can know the time
            - or else , from the code/program that you wrote , from that code you can also find the time complexity <br>
                if there's a for loop , we're going from 0 to last element i.e `i < n` means it's `n` <br>
                means it's taking O(n) times , so whatever inside the for loop body , that thing will repeat `n` times <br>  
                so we can analyse based on the procedure also or based on the code/program also
        - Eg : let's say we're on first element of that array , & we're analyzing all the other further elements inside that array
            - & again begin on the 2nd element of that array , we're analyzing all the next further elements <br>
                let's assume that you're comparing for sorting purpose
            - so with 2nd element , we're comparing further each of the elements & same thing we'll do for each elements <br>
                so for one element , we're checking all the elements & then next element , it'll check for all means processing for all
            - so here `n` elements are begin processed `but for how many times` <br>
                so for each elements `n` elements are processed , so it'll be `n * n = n²` , so we can say `O(n²)` 💡💡💡
            - so for processing/writing code for sorting will look like this 
                ```js
                for (let i = 0; i < n; i++) {
                    for (let j = i+1 ; j < n; j++) {
                        /* 
                            here we write our logic
                         */
                    }
                }
                ```
                - so when you have two nested for loops , then it's `n²` , so you don't have to check line by line <br>
                    so just look at the code , you got the rough idea but check the code thorougly , so you don't miss any line 💡💡💡
        - Eg : now let's say , being on the first element , we're processing rest of the elements , so `n - 1` elements we're processing 
            - now being on the second element , we're processing rest of the elements <br>
                but we're not processing first one so it'll be n - 2 + n - 1
            - now being on the third element , we're processing rest of the elements , right now just imagine that you're doing something <br>
                so it'll become & go on reducing & finally we'rell get this `1 + 2 + 3 + 4 + ..... n - 3 + n - 2 + n - 1` <br>
                & this means `n(n - 1)/2` means sum of first `n` natural numbers
            - so that'll become `n² - n / 2` , so here what's the degree of this `n²` polynominal i.e n² so , O(n²) like this 
                ![degree/order of the polynomial](../notes-pics/06-lecture/abdul-bari/lecture-6-2.png)
        - Eg : now let's say we're taking `4th index` element of that array & assume that 4th index element is the middle element 
            - & again consider before that elenent is the middle element like this <br>
                ![consider those elements as middle element](../notes-pics/06-lecture/abdul-bari/lecture-6-3.png)
            - so we're not processing the entire elements . we're processing half - half array , <br>
                so that process will always be divided by 2 . so when something is successively divided until it reaches 1 <br>
                that is represented as `log₂n` means log₂ of n elements & here we're dividing by 2 that's why we took `2` <br> 
                so the time complexity will be logn
            - so the code will look like this
                ```js
                for (let i = n; i > 1; i=i/2) { // here every time , we'll divide by 2
                    /* 
                        write logic
                     */
                }
                ```
                - now just look at the for loop , don't tell bindly order of n , read how the for-loop is behaving
                - so how we got `log₂n` , so if the value of i is getting divided by 2 everything <br>
                    then it's `log n` & we got `n` because we're diving n no. of elements & we're dividing by 2 <br>
                    so ultimately , time complexity will be `log₂n` like this <br>
                    ![log2n](../notes-pics/06-lecture/abdul-bari/lecture-6-4.png)
                - & how long it's happening , until for loop reaches 1 , that's why we use `log` 💡💡💡 <br>
                    & same thing will be happen if we use while loop also
            - `Note : when to use while loop 🔥` : 
                - usually , when we're not incrementing by 1 every time then instead of using for loop 
                - use the while loop , but you can for loop also 
                - but for loop , usually used for like a counter which is incrementing by 1 💡💡💡
            - so we see both ways to get the time complexity from the code & from the work/procedure <br>
                & if you're analyzing from the work/process that's more better

    - Eg : of linked list & it same as array which we'll see in next lecture
    - Eg : a matrix , 
        - so in this picture , we have the matrix of 4 * 4 means 4 by 4 like this <br>
            ![matrix example](../notes-pics/06-lecture/abdul-bari/lecture-6-5.png)
        - so total how many elements , so if dimension is n * n then total elements will be `n²` <br>
            so time complexity will be `O(n²)`
        - so when you're processing up on a matrix then it'll require N square amount of time , <br>
            if you're processing on all the elements
        - if you say that you're processing a row then time complexity will be `O(n)` <br>
            if you're processing a column so again it's `O(n)` , if you're processing all the elements <br>
            which require 2 loops then time complexity will be `O(n²)`
        - program of looping over the matrix
            ```js
            for (let i = 0; i < n; i++) {
                for (let j = 0; j < n; j++) {
                    /* 
                    ------
                    ------
                    -----
                     */
                }
            }
            ```
            - & let's say you having a loop or a functions which has a loop inside this second nested loop <br>
                then the time complexity for those total 3 loops i.e `n³` means n cube 
        - if you're processing only one statement or two statements which don't have any loops then time complexity is `O(n²)`

    - eg : of array of linked list <br>
        ![array of linked list](../notes-pics/06-lecture/abdul-bari/lecture-6-6.png)
        - so total how many elements are there i.e `n` , so total how much processing you're required <br>
            so we can say `O(m + n)` processing is required but if you say that you want to consider only `n` elements <br>
            which are present right now then you can say total processing is `O(n)` 💡💡💡
        - we're not considering `m` because it's totally depends on situation whether we need to include or not <br>
            so you're processing for `m` also but you don't want to consider the time taken by `m`

    - eg : of binary tree <br>
        ![binary tree example](../notes-pics/06-lecture/abdul-bari/lecture-6-7.png)
        - & total elements are 7 elements . now let's say you're processing like for searching 
        - & suppose , you're searching via branch/path , so at the bottom , we have some elements <br>
            & when you go up then we need to divided by 2 & divide by 2 until it reaches 1 element 
        - so time complexity will be `log₂n`
        - but if you're spending time on a tree along with the height of the tree then we'll get `O(logn)`
        - if you want to process on each element then how many elements are there i.e `n` <br>
            so time complexity will be `O(n)` 💡💡💡
        - now if you write the code for this program then time complexity will be `order of n -> O(n)` <br> 
            but analyze the code properly 

    - so time complexity is actually depends on work that you're doing 💡💡💡

- space complexity : 
    - we want to know how much spaces is consumed in main memory during the execution of the program
    - Eg : in that same array , total 7 elements are there but in future it could be any number of times <br>
        so total `n` elements are there 
    - here we're not calculating bytes , we want to know the spaces dependent on what i.e `n` <br>
        so if the value of `n` is more then the spaces will be more 💡💡💡
    - Eg : of linked list 
        - so along with the elements we the space for links also , so let's say 2n , so again `O(n)`
    - Eg : of matrix 
        - space complexity will be `n^2`
    - Eg : of array of linked list 
        - space complexity will be `m + n`
    - Eg : of binary tree
        - here n nodes are there , so space complexity will be `O(n)`
    - here we'll see examples , & just by looking at the program code without look at the process , we'll take out time complexity 

- Eg : calculating time & space complexity
    - how to analyze , so we assume that every simple statement in a function or a program takes 1 unit of time <br>
        & what is simple statement ? , means the statement may be having automatic operations assignment or a conditional <br> 
        statement if it's more complex then we have to study that also in detail
    - Example 1 : of swap code <br>
        ![swap code](../notes-pics/06-lecture/abdul-bari/code-1.png)
        - here we're inter-changing the value of x & y
        - & each statement will take 1 unit of time because those are just an assignment , so total time is 3 <br>
            so the `f(n) = 3` like this <br>
            ![swap code](../notes-pics/06-lecture/abdul-bari/code-2.png)
        - so here 3 is constant like this O(1) 
        - & `why it's contant` : because here degree of n is 0(zero) , so power of 0 is equal-to O(1) like this
            ![swap code](../notes-pics/06-lecture/abdul-bari/code-3.png)
    - Example 2 : of sum code <br>
        ![sum code](../notes-pics/06-lecture/abdul-bari/code-4.png)
        - here `s = 0` will take 1 unit of time
        - now in for loop , first we have assignment then condition then assignment 💡 <br>
            & this for loop will not be executed only one time , it'll execute for `n` times
        - so initially , `i = 0` will run only 1 time & that increment `i++` will happen `n` times <br> 
            & condition also `i < n` will run n times but if one time condition will fail , so it'll stop <br>
            so time of that condition will be `n + 1` 💡💡💡 
            ![sum code](../notes-pics/06-lecture/abdul-bari/code-5.png)
            - so time will be `n + 1` if we're not taking constant or `2(n+1)` if we're taking constant
        - now `s = s + A[i]` is assignment & arithmetic operator , so this will execute as long as our loop is running <br>
            so how many times it'll run i.e `n` times 💡💡💡 & `return s` will run 1 time 
        - calculate totla time , so first 2n comes becuz there're two times n & 1 are 3 times , so total time will be like this <br>
            ![sum code](../notes-pics/06-lecture/abdul-bari/code-6.png)
            - so basically , when you have only one for loop then time complexity will be O(n) or order of n
            - or we can read & get the total time complexity , so we know we have 2 ways to calculate the time complexity
        - so you ask questions from yourself in order to get the time complexity ✅
            - like we're doing sum of all elements in an array
            - so how much it'll take , so it depends on number of elements 
            - how many elements are there i.e n elements
            - so time is how much i.e O(n)
    - Example 3 : matrix addition <br>
        ![matrix addition](../notes-pics/06-lecture/abdul-bari/code-7.png)
        - so outer for loop will take `n + 1` time
        - now inner loop will take `n` & that statement inside inner loop , will also take n time like this
            ![matrix addition](../notes-pics/06-lecture/abdul-bari/code-8.png)
        - now how much total time will take that inner loop , so shall we write n + 1 or n * (n + 1) <br>
            so we have nested loop , so it should be multiplication 💡💡💡
        - & that statement which is inside that inner loop , will repeat n more times , so n * n
        - now we can make a function to calculate total time like this <br>
            so `n * n` & `n * n` will be `2n^2` & `+` then 2n (becuz we have 2 times n) & then + 1 like this
            ![matrix addition](../notes-pics/06-lecture/abdul-bari/code-9.png) <br>
            so this is time that we got
        - so skip the constant & skip those number which are less than `n^2` so we'll get `O(n²)`
        - now we're saying order of n^2 but you can say big O of n^2 like this `O(n²)` <br>
            or theta of n² -> θ(n²) or omega of n²
        - so other Asymptotic notation we'll see at the end of the lecture
    - Example 4 : function with loop <br>
        ![loop inside function](../notes-pics/06-lecture/abdul-bari/code-10.png) <br>
        - so inside func2() is will take 1 , so func1() will take O(1) , this answer is wrong
        - because func2() contain a loop , so that loop will take order of n times , so it'll be `n` <br>
            so the time is taken by the func2() is not 1 , it'll be n , so that's why func1() will also take n 
        - so total time will be taken by func1() i.e O(n) 💡💡💡
        - so mostly , loops makes time as n or n^2 or n^3 ,so it's depends on loop that you're using 💡💡💡 <br>
            & same concept will be same for while loop also
        - but the loop is behaving in a different way like logn or something else then you need to read the code <br>
            then get the time complexity 

## lecture - Kunal Kushwaha

## lecture - codebasics YT

## lecture - LetMeCode YT

## lecture - love babbar

## lecture - neso academy






