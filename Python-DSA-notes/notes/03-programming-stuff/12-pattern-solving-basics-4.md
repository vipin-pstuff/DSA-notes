# Pattern Solving - basics 4

## lecture - 4 : love babbar paid course

- square pattern
    - Eg : to solve the pattern problem , we need a little bit analytical mindset    
        - & the data which're available we have i.e `row` , `col` & `n`
        ![analytical mindset to solve pattern problem](../../notes-pics/12-lecture/love-babbar/lecture-12-0.png)
        - so in `1st row` : we have 4 stars <br>
            `2nd row` : we have 4 starts <br>
            `3nd row` : we have 4 starts <br>
            `4nd row` : we have 4 starts 
    - so we can make no. of rows & columns based on that `n` value like this 
        ```cpp
        #include <iostream>
        using namespace std;

        int main() {
            int n = 4 ; 
            for (int row = 1; row <= n; row++) {
                // for each row , print n stars or we have n col
                for (int col = 1; col <= n; col++) {
                    cout << "*";
                }
            }
        }
        ```    
        - if we just do this then we'll get output or not , So answer is No , because after every row <br>
            we're printing on new line , so we need `endl` 💡💡💡
        ```cpp
        #include <iostream>
        using namespace std;

        int main() {
            int n = 4 ; 

            // for rows
            for (int row = 1; row <= n; row++) {
                // for each row , print n stars or we have n col
                for (int col = 1; col <= n; col++) {
                    cout << "* ";
                }
                cout << endl; // cout << '\n';
            }
        }
        ```    
        - so for each row , we're printing stars from 1 to 4

- left half pyramid
    - so input is for `n` is 5 & we can represent the half pyramid like this
        ![diagram representation of half pyramid](../../notes-pics/12-lecture/love-babbar/lecture-12-1.png)
    - for first outer loop will run 5 times , now we need to under for each row what we need to do 💡💡💡 <br>
        so here for 1st row , only 1 star printing <br>
        for 2nd row , only 2 star printing <br>
        for 3rd row , only 3 star printing <br>
        for 4th row , 4 star printing 
    - so that's why star count = row number 💡💡💡 , so loop will run from column 1 to row no.
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {
        int n = 4 ; 

        // for rows
        for (int row = 1; row <= n; row++) {

            // for each row , print stars based on row number
            for (int col = 1; col <= row; col++) {
                cout << "* ";
            }

            // after every row
            cout << endl; // cout << '\n';
        }
    }
    ```

- inverted left half pyramid
    - so for 1st row , we're printing 4 stars , so formula is `(n - row) + 1` 
        ![getting output based on this formula](../../notes-pics/12-lecture/love-babbar/lecture-12-2.png)
        ![3 things which are important to find the star count](../../notes-pics/12-lecture/love-babbar/lecture-12-3.png)
    - so that's why based on this , we can make a formula i. `(n - row) + 1`
        ![calculating whether we're getting correct answer via this formula equalto our stars on each row](../../notes-pics/12-lecture/love-babbar/lecture-12-4.png)
    - `Note ✅` : here in formula , why we took `+ 1` because we run `row from 1 to n` but if we run row from 0 to n <br>
        then we don't need that `+ 1` in formula like this
        ![why we took + 1 in formula](../../notes-pics/12-lecture/love-babbar/lecture-12-5.png)
    - but if you don't want to apply this formula , then you can use counter so on each row counter is decrementing like this 
        ![another way to solve this pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-6.png) 
        - so we can run logic for `row` based on `n` like this 
        ![another way to solve this pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-7.png) 
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n ;
        cin >> n ;
         
        for (int row = 1; row <= n; row++) {
            for (int col = 1; col <= ((n - row) + 1); col++) {
                cout << "* " ;
            }    
            
            cout << endl;
        }

        return 0;
    }
    ```

- right half pattern 
    ```
            * 
          * * 
        * * * 
      * * * * 
    * * * * * 
    ```
    - so in 1st row , we have 3 space then 1 star <br>
        in 2nd row , we have 2 spaces then 2 star <br>
        in 3rd row, we have 1 space then 3 star <br>
        & we don't have any space
    - so from 1st to 3rd row , we're printing two things in each row i.e space & star , <br>
        so we'll get that triangle which we already did like this 
        ![understanding the concept to solve this pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-8.png)
        ![understanding the concept to solve this pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-9.png)
        ![understanding the concept to solve this pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-10.png)
    - so eg : in 1st row , we need 3 spaces , so how you'll make 3 i.e `n = 4` & row is 1st , <br>
        so if we do `n - row` , we'll get `3` like this 💡💡💡 <br>
        ![how you'll make 2 thing in each row except in 4th row](../../notes-pics/12-lecture/love-babbar/lecture-12-11.png)
    - so you need to observe & game is over 👍
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n ;
        cin >> n ;
         
        for (int row = 1; row <= n; row++) {
            // for each row

            // spaces
            for (int col = 1; col <= n-row; col++) {
                cout << " " ;
            }    

            // stars
            for (int col = 1; col <= row; col++) {
                cout << "* " ;
            }    

            // after each row
            cout << endl ;
        }

        return 0;
    }
    ```

- right inverted half pattern
    ![right inverted half pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-12.png)
    - so previously , we did those triangles pattern <br>
        ![spaces we have](../../notes-pics/12-lecture/love-babbar/lecture-12-13.png)
    - so first count , in 1st row , how much space & stars do you have & same with other rows like this 
        ![count spaces & stars for each row except last row](../../notes-pics/12-lecture/love-babbar/lecture-12-14.png)
    - so we can see that whatever row number is decrementing by `1` to get the spaces , 💡💡💡 <br>
        so space formula is `row - 1` like this <br>
        ![finding formula for spaces](../../notes-pics/12-lecture/love-babbar/lecture-12-15.png)
    - for finding star , we'll have this formula i.e `n - row + 1` like this 💡💡💡 <br>
        ![finding formula for star](../../notes-pics/12-lecture/love-babbar/lecture-12-16.png)
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n ;
        cin >> n ;
         
        for (int row = 1; row <= n; row++) {
            // for each row

            // spaces
            for (int col = 1; col <= row-1; col++) {
                cout << " " ;
            }    

            // stars
            for (int col = 1; col <= (n-row)+1; col++) {
                cout << "* " ;
            }    

            // after each row
            cout << endl ;
        }

        return 0;
    }
    ```
    - so after this we can have multiple approaches to solve this problem or any particular problem in programming <br>
        & we can optimize it more 
    - `Note` : if we use <= or any conditional based operator then at the end , it'll converted into true or false 💡💡💡 
    - so till yet we saw these patterns
        ![patterns that we didn't till yet](../../notes-pics/12-lecture/love-babbar/lecture-12-17.png)

- homework 
    - print solid diamond pattern like this 
        ![approach to print diamond pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-18.png)
        - so we need to divide each pattern into 4 parts to solve it
        - we just need to find the formula for inner loops condition
    - hollow left inverted half pyramid , inverted solid full pyramid , hollow full pyramid
        ![patterns picture](../../notes-pics/12-lecture/love-babbar/lecture-12-19.png)

- to make formula, just wrote the things that you have available like row , value of n & whatever is available <br>
    & observe how to make formula

- full solid pyramid
    - `Note ✅` : if you'r starting loop from 0(zero) < n then put formula i.e `n - row` <br>
        but if you're starting from `n - row + 1` 💡💡💡
        - but you're starting loop from 1 to n then put `1 <= n` then you have to use `n - row + 1` formula 💡💡💡
    - so this pattern , we need to print & it's half part looks like previous pattern i.e right half pattern like this 
        ![patterns that we didn't till yet](../../notes-pics/12-lecture/love-babbar/lecture-12-20.png)
    - approach to make formula , write down all rows , count spaces & starts in each row like this 💡💡🔥
        ![approach to find the formula of a pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-21.png)
    - so first outer loop , will run row from 1 to n , & for space n - row & for star 1 to row
    - so ultimately game lies here i.e finding formula for condition 💡💡💡<br>
        ![approach to find the formula of a pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-22.png)
        - so here first inner loop is to find space & second inner loop is to print stars
        - to find formula for condition , just use approach like we have `row = 1` & `n = 4` & need to make 3 <br>
            so how you'll make i.e `n - row` , so same way row is 1 & star is 1 in 1st row of pyramid star pattern 💡💡💡
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n = 5;         

        for (int row = 1; row <= n; row++) {

            // for each row
                // spaces
                for (int col = 1; col <= n-row; col++) {
                    cout << " " ;
                }    

                // stars
                for (int col = 1; col <= row; col++) {
                    cout << "* " ;
                }    

                // after each row
                cout << endl ;
        }

        return 0;
    }
    ```

- homework : full inverted star pyramid 
    ```
      * * * * *
       * * * *
        * * *
         * *
          *
    ```
    ![making formula for space](../../notes-pics/12-lecture/love-babbar/lecture-12-23.png)
    ![making formula for star](../../notes-pics/12-lecture/love-babbar/lecture-12-24.png)
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n = 4 ;
        
        for (int row = 1 ; row <= n ; row++) {
            
            // for each row 
                // for spaces
                for (int col = 1 ; col <= row-1 ; col++) {
                    cout << " ";
                }
                
                // for stars
                for (int col = 1 ; col <= (n-row)+1 ; col++) {
                    cout << " *";
                }
            cout << endl;
        }
        
        return 0;
    }
    ```

- hollow left inverted half pyramid
    ```
    *****
    *  *
    * *
    **
    *
    ```
    - approach to solve hollow left inverted half pyramid 💡💡💡
        ![approach](../../notes-pics/12-lecture/love-babbar/lecture-12-25.png)
        ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-26.png)
    - why we're handling that 1st row & last row separately because we're getting that pattern like this 
        ![reason why we're handling first & last row separately](../../notes-pics/12-lecture/love-babbar/lecture-12-27.png)
        - so we have 2 spaces then 1 space then 0 space & then 0 space which is not creating any pattern 
        - that's why we're dividing our logic on 2 parts 
    - logic of code 💡💡💡
        ![logic of code](../../notes-pics/12-lecture/love-babbar/lecture-12-28.png)
    - now we need of find out formula 
        - for first row & last row , Eg : we have `row = 1` & `n = 5` & you need to make `5` <br>
            so how you gonna make i.e `n - row + 1` i.e `3 - 1 + 1` 💡💡💡 like this
            ![logic of code - for 1st & last row](../../notes-pics/12-lecture/love-babbar/lecture-12-29.png)
        - now for middle , we need to find out formula , Eg : in 2nd row i.e `row = 2` & `n = 5` <br>
            we need to print 2 spaces i.e `n - row - 1` & you can check for 100% that it's working for every situation or not <br>
            so formula will be this 
            ![logic of code - for middle pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-30.png)
    ```cpp
    #include <iostream>
    using namespace std;

    int main() {

        int n = 6;

        for (int row=1; row<=n; row++) {

            // for first & last row
            if (row == 1 || row == n) {
                // stars
                for(int col=1; col<=n-row+1; col++) {
                    cout <<"*";
                }

            // for middle rows
            } else {
                cout << "*";
                // space
                for(int col = 1 ; col <= (n - row) + 1 ; col++) {
                    cout <<" ";
                }
                cout << "*";
            }

            // after each row
            cout << endl;
        }

        return 0;
    }
    ```

- `note` : in pattern problems, game always stuck on finding formula for conditions 👨‍🏫

- homework 
    - in first diagram , numbers half left pyramid , we're just printing column number 
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-31.png)
    ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-32.png)
    - divide this diamond pyramid in two parts <br>
        ![diamond pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-33.png)
    - numbers pattern <br>
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-34.png)
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-35.png)
    - pascal triangle <br>
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-36.png)
    - divide this pattern in four parts to solve or you can divide it into major 2 parts <br>
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-37.png)
    - butterfly pattern , you can divide this into 4 parts or into 2 parts <br>
        ![butterfly pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-38.png)
    - star pattern
        ```
          *********
           *******
            *****
             ***
              *
        ```

- doubts
    - pascal triangle <br>
        ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-36.png)
        - we can solve this via formula of combination like this
            ![numbers pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-55.png)
            - here `n` is row & `r` is column 💡💡💡
        - approach 
            - create a function which return the value of `nCr` <br>
                so that function takes 2 parameter i.e row & col & inside of it create outer & inner loop <br>
                outer loop wil run from 0 to `<n` & inner loop will run 0 to row <br>
                & we can create another function which return factorial 
                - Note : we can't find factorial of big number because of max size of integer
            - code approach
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-56.png)
                - we can use `long` datatype in order to avoid integer overflow error
            - another approach
                - we can do with array , so we need 2D array
    - butterfly pattern
        ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-57.png)
        - so this pattern will be divided into 4 parts
        - code structure will be this 
            ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-58.png)
    - hollow diamond pattern 
        - approach
            - pattern will look this 
                ![code approach ](../../notes-pics/12-lecture/love-babbar/lecture-12-59.png)
            - so code of that small part
                ![code approach ](../../notes-pics/12-lecture/love-babbar/lecture-12-60.png)
            - code of another small part
                ![code approach ](../../notes-pics/12-lecture/love-babbar/lecture-12-61.png)
            - & same thing with bottom half one will be solved , so this pattern will be solved into 4 parts
            - so put those both half part inside a loop which print the half top pattern 💡💡💡 & same with bottom one
        - Advice : 
            - so before we're not able to solve this problem so we break it down into half then again not able to solve <br> 
                so we again break that half into another half 
            - & we solved it , so if a problem is big & you're not able to solve it then break it down <br>
                in order to get the approach 
    - different types of solid half diamonds
        ```
        *
        * 1 *
        * 1 2 1 *
        * 1 2 3 2 1 * 
        * 1 2 1 *
        * 1 *
        * 
        ```
        - understanding 
            - we're seeing that starting & ending is star , except first & last row 
            - & in the middle , number is staring from 1 & after a point , number get reverse
            - so in code form , it'll look something like this
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-62.png)
            - in 2nd row case , counting goes till 1 <br>
                in 3rd row case , counting goes till 2 & then reverse
                in 4th row case , counting goes till 3 & then reverse like this
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-63.png)
            - understanding via code sample 💡💡💡
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-64.png)
            - now can my code run , so let's write the code 
                ```cpp
                void printPattern(int n) {
                    for (int row=1; row <=n; row++) {
                        
                        if (row == 1 || row == n) 
                            cout << "*" << endl;
                        else {
                            cout << "* ";
                            // logic
                            int counter = 1;

                            // increasing order
                            while(counter != row - 1) {
                                cout << counter << " ";
                                counter++;
                            }

                            while(counter > 0) {
                                cout << counter << " ";
                                counter--;
                            }

                            cout << " *" << endl;
                        }
                    }
                }

                int main() {
                    int n = 7 ;

                    printPattern(n) ;

                    return 0;
                }
                ```
                - output : we'll get half part
                    ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-65.png)
                - now we need to think about logic for 5th row to 7th row
        - brainstorming
            ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-66.png)
            - actually , we're making mistake on value of `n` which we're taking <br>
                so if we take `n=4` then we'll able to print that half part
            - assume that value of n is `4` and 
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-67.png)
                - so that logic part is print numbers from `1` to `n-row-1` then come back to decreasing order till 1
        - advice + code approach
            - so basically , first time we're solving the problem & we don't know anything but we want to solve it 
            - first code part approach is like this 💡💡💡
                ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-68.png)
                - so when we put define `n = 4` , then we'll get this output instead of getting half pattern properly
                    ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-69.png)
                - so problem is on this condition `if (row == 1 || row == n)` , so remove this `row == n` from the code <br>
                    then we'll get that half pattern output properly like this
                    ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-70.png)
                - now we need to write code for lower half 
            - another code approach 
                - there's also code available which can be done in one nested loop
            - but if you don't know then solve the problem by breaking it into smaller problem 
    - square repeating number pattern
        ```
        3 3 3 3 3   
        3 2 2 2 3   
        3 2 1 2 3   
        3 2 2 2 3   
        3 3 3 3 3     
        ```
        - understanding approach
            ![code approach](../../notes-pics/12-lecture/love-babbar/lecture-12-71.png)

## lecture - Love babbar YT video

- number pattern <br>
    ![number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-39.png)
    ![reverse number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-40.png)
    ![reverse number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-41.png)
    ![reverse number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-42.png)
    ![reverse number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-43.png)
- characters pattern <br>
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-44.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-45.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-46.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-47.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-48.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-49.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-50.png)
    ![character pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-51.png)
- number pattern <br>
    ![number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-52.png)
    ![number pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-53.png)
- star + number pattern <br>
    ![number + star pattern](../../notes-pics/12-lecture/love-babbar/lecture-12-54.png)

## lecture - kunal khushwaha

- patterns which is not inside love babbar course
    ```
     * * * * *
      * * * *
       * * *
        * *
         *
         *
        * *
       * * *
      * * * *
     * * * * *
    ```
    ```
           *
          * *
         *   *
        *     *
       *********
    ```
    ```
        *********
         *     *
          *   *
           * *
            *
    ```
    ```
              1
            1   1
          1   2   1
        1   3   3   1
      1   4   6   4   1
    ```
    ```
           1
          212
         32123
        4321234
         32123
          212
           1
    ```
    ```
       ****
       *  *
       *  *
       *  *
       ****
    ```
    ```
           *      *
         *   *  *   *
       *      *      *
    ```
    ```
       *        *
       **      **
       * *    * *
       *  *  *  *
       *   **   *
       *   **   *
       *  *  *  *
       * *    * *
       **      **
       *        *
    ```
    ```
          *****
         *   *
        *   *
       *   *
      *****
    ```
    ```
      1 1 1 1 1 1
      2 2 2 2 2
      3 3 3 3
      4 4 4
      5 5
      6
    ```
    ```
        1 2 3 4  17 18 19 20
          5 6 7  14 15 16
            8 9  12 13
              10 11
    ```
    ```
            1
          2 1 2
        3 2 1 2 3
      4 3 2 1 2 3 4
    5 4 3 2 1 2 3 4 5
    ```
    ```
         4 4 4 4 4 4 4  
         4 3 3 3 3 3 4   
         4 3 2 2 2 3 4   
         4 3 2 1 2 3 4   
         4 3 2 2 2 3 4   
         4 3 3 3 3 3 4   
         4 4 4 4 4 4 4 
    ```
    ```
       a
       B c
       D e F
       g H i J
       k L m N o
    ```
    ```
       E D C B A
       D C B A
       C B A
       B A
       A
    ```
    ```
       1      1
       12    21
       123  321
       12344321
    ```

- in interview , no one is going to asking pattern topics questions <br>
    these questions are important if you're starting programming first time then it'll build the foundation 👍

- prerequisite : loop

- `how to approach a pattern problem` : ✅
    - `STEP 1` : run the outer loop for that number of rows 
        - so no. of lines = no. of rows = no. of times outer loop will run
    - `STEP 2` : identify for every row number
        - `1` : how many number of cols are there
        - `2` : type of elements in each columns
    - `STEP 3` : what do you need to print like star or numbers

- solving Pattern Question :  
    ```
    *
    **
    ***
    ****
    *****
    ****
    ***
    **
    *
    ```
    - solution : 
        ![star pattern](../../notes-pics/12-lecture/kunal-kushwaha/lecture-12-0.png)
        ![star pattern](../../notes-pics/12-lecture/kunal-kushwaha/lecture-12-1.png)
        - & outer loop will run 2 times that's why 2 * n
        - so code is <br>
            ![star pattern](../../notes-pics/12-lecture/kunal-kushwaha/lecture-12-2.png)
        - but we'll get wrong output like this <br>
            ![output](../../notes-pics/12-lecture/kunal-kushwaha/lecture-12-3.png)
        - problem is inside the formula ✅
            ![output](../../notes-pics/12-lecture/kunal-kushwaha/lecture-12-4.png)
            - then we'll get correct output
        - so we solve this pattern by using only one inner loop , but in love babbar , <br>
            we solved by using two inner loop

- Note : whenever you're dealing with pattern numbers , then start loop from `1` , not 0

## patterns took from google 

```
6 6 6 6 6 6 
6 6 6 6 6 
6 6 6 6 
6 6 6 
6 6 
6
```
```
6 6 6 6 6 6 
5 5 5 5 5 
4 4 4 4 
3 3 3 
2 2 
1
```
