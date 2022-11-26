# Array problems - questions

## lecture 8 - love babbar (paid course) - Array problems 

- `2nd Ques` : reverse an array
    - understanding the question
        - input : `[3, 5, 2, 7, 6, 9]`
        - output : `[9, 6, 7, 2, 5, 3]`
        - here we're just changing the position of elements of an array like this
            ![need to reverse like this](../../notes-pics/15-1-lecture/love-babbar/lecture-15-0.png)
    - approach 
        - so let's say i putted `i` index at 0 index & `j` on last index i.e `n - 1` 
        - & now we just need to swap & we need to do this till `i < j` , so we need to run loop like this
            ![approach like this](../../notes-pics/15-1-lecture/love-babbar/lecture-15-1.png)
    - code 
        ```cpp
        void reverseArray(int arr[], int n) {
            int i = 0 ;
            int j = n - 1;

            while(i < j) {
                swap(arr[i], arr[j]) ;
                i++ ; 
                j-- ;
            }
        }

        int main() {
            int arr[] = {3, 5, 2, 7, 6, 9}

            reverseArray(arr, 6)

            // print the array
            for (int i=0; i<arr.length; i++) {
                cout << arr[i] << " ";
            }

            cout << endl;
        }
        ```
    - what is swap ? <br>
        ![swapping](../../notes-pics/15-1-lecture/love-babbar/lecture-15-2.png)
        - we can also do swapping via `XOR` bitwise operator or we can use `+` & `-` arithmetic operator 💡
    - dry run code 💡💡💡
        ![dry run](../../notes-pics/15-1-lecture/love-babbar/lecture-15-3.png)
        - so here we can see that middle element doesn't get swapped & middle element stays on same place <br>
        - so we're just swapping elements together which are left & right side of that middle element
        - & let's say we don't have swap in-build function <br>
            then we can write the code like this
            ```cpp
            // swapping code
            int a = 2 ;
            int b = 3 ;
            int temp = a ;
            a = b ;
            b = temp;
            ```
        - & if we can do `i <= j` also in while condition <br>
            because that middle number will be swapped by itself , but it doesn't make any sense that's why we didn't did 💡💡💡 
    - time complexity of reversing an array 
        - so we have an array & starting index is `i` & ending index is `j` <br>
            & we divided that array into 2 parts , so `n/2` operation is happening 
        - so `O(n/2)` but we remove the constant , so time complexity is `O(n)` of reversing an array


- `3rd question` : 
    - `3.1 ques` : find max number in an array ?
    - input : `[3, 12, 7, 18, 17, 16]`
    - O/p : 18
    - understanding 
        - initially , we'll assignment a min number in order to compare with each elements of an array like this
            ![understanding the question](../../notes-pics/15-1-lecture/love-babbar/lecture-15-4.png)
        - but we can make our own max function like this
            ```cpp
            int getMax(int a, int b) {
                if (a > b) {
                    return a;
                } else {
                    return b;
                }
            }
            ```
    - code 
        ```cpp
                        //   array      size of the array
        int getMaxFromArray(int arr[], int n) {
            int ans = INT_MIN;

            for (int i=0; i<n; i++) {
                ans = max(ans, arr[i]) // max() function is a pre-defined function in c++
            }

            return ans;
        }

        int main() {
            int arr[] = {3, 5, 7, 6, 9, 2, 5} ;

            reverseArray(arr, 7);
            cout << "Maximum value is " << getMaxFromArray(arr, 7) << endl ;
        }
        ```
        - if error `not defined` comes for `INT_MIN` then , just use `#include <limits.h>` <br>
            before `using namespace std` statement
    - code dry run
        ![dry run](../../notes-pics/15-1-lecture/love-babbar/lecture-15-5.png)
        - so here we're doing linear search
    - Note : why we initialize `ans` variable as INT_MIN -> `int ans = INT_MIN` , ✅
        - because let's say if we take `0` then we're not able to check <br>
            what if in array all numbers are in negative , then our answer will be `0` like this 💡💡💡
            ![why we took INT_MIN](../../notes-pics/15-1-lecture/love-babbar/lecture-15-6.png)
        - so here max number is `-1` inside that array , so let's say if we initialize `ans = 0` 
        - then here in this situation i.e we have negative elements inside of an array <br>
            then our answer gets wrong , that's why we're taking `INT_MIN` , instead of `0` or any number 💡💡💡
    - in c++ , integer has a range i. `-2^31` -> for INT_MIN & `2^31 - 1` for INT_MAX 💡💡💡 
    - `3.2 ques` : find a min number from an array ?
        - what we need to change in code 
            - `STEP 1` : use `INT_MAX` for ans -> variable
            - `STEP 2` : change max() into min() function where we used it
        - code 
            ```cpp
            int getMaxFromArray(int arr[], int n) {
                int ans = INT_MAX;

                for (int i=0; i<n; i++) {
                    ans = min(ans, arr[i])
                }

                return ans;
            }

            int main() {
                int arr[] = {3, 5, 7, 6, 9, 2, 5} ;

                reverseArray(arr, 7);
                cout << "Maximum value is " << getMaxFromArray(arr, 7) << endl ;
            }
            ```
    - code to print min & max both from a function, then we can use pair in C++
        ```cpp
        pair<int, int> getMaxMinFromArray(int arr[], int n) {
        	int maxi = INT_MIN ;
        	int mini = INT_MAX ; 
        	
        	for (int i=0; i<n; i++) {
        		maxi = max(maxi, arr[i]) ;
        		mini = min(mini, arr[i]) ;
        	}
        	
        	pair<int, int> p = make_pair(maxi, mini) ;
        	return p;
        }
        ```

- `4th question` : swap alternate or adjacent elements of array
    - input : `[2, 7, 5, 6, 9, 8]`
    - O/P : `[7, 2, 6, 5, 8, 9]`
    - understanding 
        - let's say we have an array `[2, 7, 5, 6, 9, 8]`
            ![swapping alternate or adjacent elements of an array](../../notes-pics/15-1-lecture/love-babbar/lecture-15-7.png)
    - approach
        ![approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-8.png)
        - code approach
            ![approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-9.png)
        - here wee took `i+1` i.e `i+1 < n` condition because let's say `i` is on last index of your array <br>
            & then we did `i + 1` which doesn't exist in the array & we're saying to do swap like this <br>
            then code will not work , so top stop the loop from moving forward that's why we used `i + 1 < n`
            ![reason : why we took i+1](../../notes-pics/15-1-lecture/love-babbar/lecture-15-10.png)
            ![reason : why we took i+1](../../notes-pics/15-1-lecture/love-babbar/lecture-15-11.png)
    - code 
        - 1st approach 
            ```cpp
            void swapAlternates(int arr[], int n) {
                int i = 0;

                while(i < n) {
                    if (i+1 < n) {
                        swap(arr[i], arr[i+1]) // using pre-defined swap() function in c++
                    }
                    i = i + 2;
                }
            }

            int main() {
                int arr[] = {3, 5, 7, 6, 9, 2, 5};

                swapAlternates(arr, 7);

                // print elements of the array
                for (int i=0; i<8; i++) {
                    cout << arr[i] << " " ;
                }

                return 0;
            }
            // output : 5 3 6 7 2 9 5
            ```
        - 2nd approach 
            ```cpp
            void swapAlternates(int arr[], int n) {
                int i = 0;

                while(i+1 < n) {
                    swap(arr[i], arr[i+1]) // using pre-defined swap() function in c++
                    i = i + 2;
                }
            }

            int main() {
                int arr[] = {3, 5, 7, 6, 9, 2, 5};

                swapAlternates(arr, 7);

                // print elements of the array
                for (int i=0; i<8; i++) {
                    cout << arr[i] << " " ;
                }

                return 0;
            }
            // output : 5 3 6 7 2 9 5
            ```
        - so here 3 & 5 swap each other & same happen with other adjacent elements <br> 
            but here `5` element doesn't have it's adjacent element , so it remain as it is 💡
        - both code approach is great but 1st approach is better to understand the logic
                
- `5 ques` : sort an array of 0's , 1's & 2's
    - what is sort
        - Eg : let's say you have numbers like `3, 5, 2, 1, 7`
        - so sorting means order , means put these numbers in increasing order or decreasing order 💡💡💡
        - so in increasing order , these numbers will be `1, 2, 3, 5, 7`
    - understand the question
        - let's say we have an array of combination of those 3 numbers `[1, 0, 2, 2, 0 , 1, 1]` <br>
            so let's say this is input -> `[1, 0, 2, 2, 0 , 1, 1]`
        - & we want output `[0, 0, 1, 1, 1, 2, 2]`
    - approach 
        ![code approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-12.png)
        - so actually those 3 variables , we made in order to count those no. of values <br>
            & after finding them , you put those no. of zeroes inside the array & so on with 1 & 2
        - problem with this code approach ✅
            - this code is not optimized , there's a concept i.e `three pointer approach` , so via this , we can optimized the code <br>
                we'll talk about optimize approach when we do sliding window & discuss about two pointer
            - let's say we don't know the numbers , so right now we're just taking about those 3 numbers <br>
                but if numbers grows like 50 numbers then this approach will not work 
            - you can use sorting technique instead of doing counter approach
        - another approach
            - we can use `sort() function` in c++ like this
                ```cpp
                int main() {
                    int arr[] = {1, 0, 2, 2, 0 , 1, 1}
                    int sizeOfArr = arr.length - 1; // here we can't write 7 -> as size , becuz it's hard coded value
                    sort(arr, sizeOfArr)
                    
                    for (int i=0; i<sizeOfArr; i++) {
                        cout << arr[i] << " " ;
                    }
                }
                ```
    - code 
        ```cpp
        void sortZeroOneTwo(int arr[], int n) {
            int one = 0; zero = 0; two = 0 ;

            // count all numbers
            for (int i=0; i<n; i++) { // traversing the complete array
                if (arr[i] == 0) 
                    zero++ ;
                else if (arr[i] == 1) 
                    one++ ;
                else 
                    two++ ;
            }

            int i = 0 ;
            // put zero
            while(zero--) { // here zero-- means zero != 0
                // means run the while till if zero != 0 & same with those 2 bottom while loop 💡💡💡


                arr[i] = 0; // saying put all the no. of zero inside the array
                    // here we don't need to worry about whether we're pushing 0 or 1 or 2 first
                    // see the code first we're pushing no. of zeroes 💡💡💡
                i++ ;
            } 

            // put one 
            while(one--) {
                arr[i] = 1;
                i++ ;
            }

            // put two 
            while(two--) {
                arr[i] = 2;
                i++ ;
            }
        }
        ```

- `Ques` : Check whether an array is palindrome or not
    - so we already did question i.e -> reverse an array , so here same approach we'll apply 💡💡💡
    - what is palindrome means
        - if you have an array , so when you read from `left to right` or `right to left` , then we'll get same answer
        - Eg : we have string "madam" , so if you read it from left to right or right to left , we'll get same output <br>
            so that is palindrome 
        - Eg : OYO , LOL, `DALDA` is not palindrome because first letter is `D` & last is `A`
    - understanding the question
        - Eg : we have `[1, 2, 3, 3, 2, 1]` , so if we traverse over it from left to right or right to left , we'll get same output <br>
            so this array is palindrome
    - approach 
        - we can divide this array `[1, 2, 3, 3, 2, 1]` into half
            ![code approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-13.png)
        - this code can run for characters also & for even + odd number also
    - code 
        ```cpp
        bool checkPalindrome(int arr[], int n) {
            // starting index
            int i = 0 ;
            // ending index
            int j = n - 1;

            // compare left half with right half
            while (i < j) {
                if (arr[i] == arr[j]) {
                    // if match , then check the remaining array
                    i++ ;
                    j-- ;
                }
                else {
                    // if no match , then return false
                    return false ;
                }
            }
            // entire array is traversed , so it's palindrome
            return false ;
        }

        int main() {
            int arr[] = {1, 2, 3, 3, 2, 1} ;
            
            cout << "Palindrome or not " << checkPalindrome(arr, 7) << endl ;

            return 0;
        }
        // output : Palindrome or not 1 -> here 1 means true
        // if we give {1, 2, 3, 3, 4, 2, 1} -> then we'll get output 0 -> which is false
        ```

- find union & intersection of 2 sorted arrays
    - what is union & intersection
        - Union : means unique elements , duplicate will be counted only as one time
    - understanding 
        - for finding UNION , in question , already mention that both arrays are sorted , so take 2 array 
            ![understanding](../../notes-pics/15-1-lecture/love-babbar/lecture-15-14.png)
        - the approach we used for finding UNION , there are faults
            - `1` : now let's say , in one of the array or both array , duplicate values exist <br>
                then in Union array , that duplicate value also come
                - so if we have duplicates inside an array & to check the previous element of an array <br> 
                    then we can do `i` is current index , to check previous , we can do `i - 1` 💡💡💡 <br>
                    then you can use condition i.e `i - 1 >= 0`
            - solution : we can use `set` in c++ , which used to gives the only unique values from duplicate values <br>
                we'll see about `set` when we do tree data structure
        - & same condition will goes with intersection
        - here question is not about unsorted array , so no need to worry about it
    - approach 
        - another way : we can use hashmap

- Homework Question 2 
    ![understanding](../../notes-pics/15-1-lecture/love-babbar/lecture-15-15.png)
    - in this every questions are very important 
    - Advice : tak hint , see editorial , see discussion forum , see other people's code , read article , take help of babbar bhaiya
    - in opposite side , question is can be done in that platform

- `Ques` : move all negative numbers to one side of array
    - understanding question
        - Eg : let's say we have array & that array contain positive as well as negative numbers `[3, -1, 2, -4, -6, -4, 5]` <br>
            so in input we have this array
        - we want output : `[-1, -4, -6, -4, 3, 2, 8]`
    - approach 
        - we can do sort , but if question say , we need to maintain the order then sort approach will not work <br>
            but question is just saying that we just need to put all negative numbers to one side then sort will work 
        - here we need to do swap via comparing negative with positive number
            ![approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-16.png) <br>
            here we used only two pointer i.e `i` & `j` , so kind-of we can say two pointer approach
        - & if first element is a negative number then both `arr[i]` & `arr[j]` will be swapped itself <br>
            because let's say both i & j are -1 then both will be swapped by itself 💡💡💡
        - doubts
            - what is sub-array ? 💡💡💡
                - means inside an array , we're telling from this range to this i.e sub-array
                - example of sub array
                ![what is sub-array](../../notes-pics/15-1-lecture/love-babbar/lecture-15-17.png)
            - what is sub-sequence in array ? 💡💡💡
                ![sub-sequence in array](../../notes-pics/15-1-lecture/love-babbar/lecture-15-18.png)
            - what is pair in c++ 
                - Eg : `pair<int, int> p = make_pair(1,2) ;`
                - means inside one block of memory , we can put 2 values at the same time <br>
                    & that memory named as `p` , 1st block is called first & 2nd block is called second <br>
                    first block contain `1` value second block contain `2` value like this 
                    ![sub-sequence in array](../../notes-pics/15-1-lecture/love-babbar/lecture-15-19.png)
                - so we can make pair of two different datatype like this `pair<int, char>`
                - this we'll see in STL
            - what is vector ? 
                - we learned about array , so vector is like array <br>
                    but vector concept comes in dynamic array
                - Eg : let's say we have array of 4 size & the moment size of the array gets full <br>
                    then size of that array gets doubled & let's say again that size of array fulled <br>
                    then dynamically , size of array again gets doubled 💡💡💡

- `Ques` : find duplicate in an array of (N+1) integer ? 
    - understanding the question
        - Eg : let's say you have an array as a input `[1, 2, 3, 3, 4]` 
            ![example](../../notes-pics/15-1-lecture/love-babbar/lecture-15-20.png)
    - approach
        - another example
            ![example](../../notes-pics/15-1-lecture/love-babbar/lecture-15-21.png)
        - so how they're cutting <br>
            - for input array : so basically we get the sum of each elements of an input array 
            - for that another array : eg : we already did in maths , so let's say we have `1, 2, 3, 4 ...... N` <br> 
                & we need to find the sum of it , so we can do `(n * (n + 1)) / 2` , so we'll get sum individually of both array    
            - & we'll get answer by doing `ans = sum1 - sum2`
        - code approach
            ![code approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-22.png)
            - we can't find duplicate if we have `[2, 2, 2, 2, 2]` because this question is saying <br>
                values always from 1 to N & only any one number will repeat , so this input array is wrong
        - fault on this code approach
            - if `sum > range` then we'll get error , so range of integer we already know 

- `Ques` : Kadane's Algo `google | very most imp` 🔥
    - what is Kadane ? 
        - Kadane means largest sum contiguous sub-array
        - & we already know what is sub-array
    - understanding
        - so we need to find max sum from a sub array
        ![understanding](../../notes-pics/15-1-lecture/love-babbar/lecture-15-23.png)
    - approach
        - what is brute-force  
            - means time consuming way
            - very basic way or adhoc way
            - not optimize solution based on time & space complexity 
        - approach without using kadane's algo i.e called brute-force
            ![brute-force approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-24.png)
            - means find sum of every sub-array like this 
                ```
                find every sub-array
                    - sum1 
                    - sum2 
                    - sum3 
                    - sum4

                - & then find the largest/maximum from these different sum 
                ```
        - approach via Kadane's algo
            - this game over in 3 conditions
            - so to optimize , let's say we want to do single traversal , so here comes kadane's Algo ✔️
            - how Kadane algo works ✅
                ![how kadane algo approach will work](../../notes-pics/15-1-lecture/love-babbar/lecture-15-25.png)
        - code 
            ```cpp
            #include <limits.h>
            int getMaxSubarraySum(int arr[], int n) {
                int ans = INT_MIN ; // means maxSF or max_so_far
                int maxAbtak = 0 ; // means maxEH or max_ending_here or sum

                for (int i=0; i<n; i++) {
                    // include current element
                    maxAbtak = maxAbtak + arr[i] ; // sum = sum + arr[i]

                    // update the ans
                    ans = max(ans, maxAbtak) ; // ans = max(ans, sum) ;

                    // if max ending hre is 0, them don't include
                    if (maxAbtak < 0) { // if (sum < 0)
                        maxAbtak = 0;       // sum = 0;
                    }
                }
                return ans;
            }

            int main() {
                int arr[] = {-2, -3, 4, -1, -2, 1, 5, -3} ;

                cout << "Max Subarray sum is " << getMaxSubarraySum(arr, 8) << endl;

                return 0;
            } 
            // output : Max Subarray sum is 7
            ```
            - so here we just used 3 conditions to solve this problem
        - code DRY RUN explanation via kadane's algo ✅
            - so we need largest sum of a sub-array from an array
                ![DRY RUN with kadane algo](../../notes-pics/15-1-lecture/love-babbar/lecture-15-26.png)
                - Note : why we're doing 2nd step i.e `ans = max(INT_MIN, sum)` ✅ 
                    - because in each window , we're getting update value of `sum`
                    - so we need to track which one is maximum answer <br>
                        just like we find the max number from an array & we check again & again <br>
                        so same here we're doing to track 💡💡💡
            - DRY RUN steps 
                ![STEPS - DRY RUN with kadane algo](../../notes-pics/15-1-lecture/love-babbar/lecture-15-27.png)
                - actually , we're skipping that block of an array which has negative number . so when <br>
                    we're doing `if (sum < 0) sum = 0` which means we're staring with a new window block of an array 💡💡💡
                - & we can put this condition `if (sum < 0) sum = 0` as 2nd step to understand more clearly
                ![STEPS - DRY RUN with kadane algo](../../notes-pics/15-1-lecture/love-babbar/lecture-15-28.png)
                - but if all the number is negative , then we'll get `0` as answer <br>
                    but kadane's algo says that at-least one sub-array will be there
        - time complexity 
            - time complexity in brute force solution is O(n^2)
            - of Kadane's algo is `O(n)` becuz only one loop is running till n times & here `n` means size of the array
   
    - `ques` : print that exact sub-array from which we're getting max sum of contiguous sub-array ✅
        - understanding 
            - here we need to track of starting & ending index of window/block
        - approach 
            - we'll take 2 variables : start & end variables
            - & we know that when window/block will be created , so when we got the maximum then window/block will be created <br>
                so we need to work on this line of code , so we'll put `start` & `end` variable on that starting window 
            - approach conclusion
                - we're doing 3 steps 
                    - `first` : we're including the number
                    - `second` : we're updating the answer
                    - `third` : checking `sum < 0` & then starting `new window` via `sum = 0` & skip the old window
                - so in second , 
                    - if we're updating the answer which means we got the new answer <br>
                        so getting the new answer which means we got a new window
                    - so if we got the new window then we'll save in starting or ending <br>  
                        in short , we're saying `if(sum > ans)` then do 3 things 
                        - `1st` : ans = sum means put sum inside ans
                        - `2nd` : update the start
                        - `3rd` : update the end like this
                        ```
                        if (sum > ans) {
                            ans = sum 
                            start = // store the starting index 
                            end = // store the ending index
                        }
                        ```
                - in third , 
                    - when we're starting the `new window` via doing `sum = 0` then save that starting window like this 
                        ```
                        if (sum < 0) {
                            sum = 0;
                            start = // store the starting index of the new window
                        }
                        ```
        
    - homework : kadane's algo 
        - read article (GFG) , why we made this algo , how to use kadane's algo
        - alternative of kadane's algo , different optimization 

- `ques` : unique number of occurrences - leetcode
    - understanding 
        - eg : let's say input `[3, 2, 2, 1, 3, 3]`
        - so now count how many times 1 , 2 , 3 are repeating 
        - so `1` is repeating `1` , `2` is repeating `2` times & `3` is repeating `3` times , <br>
            so we can say unique , then we can say `true`
        - but assume `3` also repeating 2 times , then we can see that `2` is repeating 2 times <br>
            & `3` is repeating 2 times , then we can answer is false ✔️✔️✔️
        - here we're checking is occurrence of each elements of an array is unique or not <br> 
            & if occurrence is unique of each number then we'll say true or if occurrence is same then we'll say false ✔️✔️✔️
    - approach
        - 1st approach 
            - `STEP 1` : we'll sort like this `[1, 2, 2, 3, 3, 3]`
            - `STEP 2` : now do counting , so `1` is coming 1 times , `2` is coming 2 times & `3` is coming 3 times
            - `STEP 3` : check is occurrence of each number of an element are unique each other or not 
                - if occurrence is unique each other then return true 
                - otherwise false 
        - 2nd approach : solving via hashmap
            - we can use `map` data structure & it's called hashmap 💡💡💡 <br>
                & data is stored inside `map` in key value form
            - Eg : of `map` data structure  
                ```cpp
                map <int, int> m;
                ```
                - this line of code mens inside the `map` , we can store integer pair `<int , int>` like this
                - advantage of storing values in key value pair i.e time complexity will be `O(1)` when we get the values 💡💡💡
            - when we go depth in `map` data structure , then we'll learn about 
                - unordered map
                - ordered map
                - hash tables
                - Self Balancing Binary Search Trees (self-balancing BST) , etc...

- `ques` : find the pair that sum to a given value `easy question | most imp 🔥`
    - understanding 
        - Eg : input : `[3, 1, 4, 5, 9, 13, 11]`
        - target : 14
        - output : let's say we want to make `14` , then return those 2 pairs through which we can make 14 ✔️
    - approach 
        - `1st` : in brute force
            - we'll do sum of 2 pairs of all elements of an array & check 
            - so to find all pairs , run outer loop from i=0 to n & inner loop from j=i+1 to n <br> 
                & time complexity of it will be O(n^2)
        - `2nd` : by using sort & two pointer 
            - time complexity of this program will be `O(n log n)` becuz time complexity of `sort()` is `n log n` 
            - process of sort & two pointer
                ![STEPS - process of sort & two pointer](../../notes-pics/15-1-lecture/love-babbar/lecture-15-29.png)
            - this same approach we'll apply on triplet sum question

- `ques` : find the triplet that sum to a given value
    - understanding 
        - input : `[1, 3, 11, 6, 13, 4]`
        - target : 23
        - output : we want 3 triplet `<_, _, _>` pairs & sum that 3 triplet pairs numbers & make the target number
    - approach
        - `1st` : in brute force
            - we'll run 3 loops like this
                ![brute force](../../notes-pics/15-1-lecture/love-babbar/lecture-15-30.png)
        - `2nd` : optimization approach
            ![optimize approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-31.png)
        - `3rd` : we can do more optimize also
                
- `ques` : minimum swaps required bring elements <= k (less equal k) together `good ques | sliding window ques`
    - understanding
        - input : `[2, 1, 5, 6, 3]`
        - now we have let's `k = 3`
        - what we need to do : 
            - bring those elements forward inside the array which are less or equal-to value of k , `<= k` , 
            - so output will be `[2, 1, 3, 6, 5]` , so here we swap b/w 5 & 3
        - output : we need to tell how much number of swaps we did , so here we did `1` time
        - so question will be like - find minimum no. of swaps required to bring elements `<=k` together <br>
            so answer will be `1` because we used 
    - approach
        ![optimize approach](../../notes-pics/15-1-lecture/love-babbar/lecture-15-32.png)
    - another same approach
        - STEP 1 : let's say we have this array `[2,1,5,6,3 ]` & given value of k is 3
        - STEP 2 : getting the size of the array which contain only those elements who are `<=k` like this
            ![STEP 2](../../notes-pics/15-1-lecture/love-babbar/lecture-15-33.png)
        - STEP 3 : taking a part of array or window & put only those elements which are `<=k`
            ![STEP 3](../../notes-pics/15-1-lecture/love-babbar/lecture-15-34.png)
        - STEP 4 : doing same process with another windows or part of an array like STEP 3
            ![STEP 4](../../notes-pics/15-1-lecture/love-babbar/lecture-15-35.png)
        - STEP 5 : now questions is saying that we need to find minimum swaps 
            ![STEP 5](../../notes-pics/15-1-lecture/love-babbar/lecture-15-36.png)
            - this concept is called sliding window because we're making window , again & again 💡💡💡
    - code 
        ```cpp
        int minSwaps(int arr[], int size, int k) {
            // find window size -> count of number <=k
            int cnt = 0;
            for(int i=0; i<size; i++) {
                if (arr[i] <= k) cnt++ ;
            }

            // create first window
            int bad = 0;
            for(int i=0; i<cnt; i++) {
                if (arr[i] > k) bad++ ;
            }

            int ans = bad;
            // check for remaining windows
            for(int i=0; j=count; j<n; i++; j++;) {
                // check old element
                if(arr[i] > k) bad-- ;

                // add a new element in a window
                if(arr[j] > k) bad++ ;

                ans = min(ans, bad) ;
            }

            return ans;
        }

        int main() {

        }
        ```
    - code explanation 👍
        - STEP 1 : get the size of the array or window which contains elements who are only `<=k`
        - STEP 2 : creating window or a part of an array , <br>
            so we're running "for loop" till count value which is the size of the array who only contains `<=k`
        - STEP 3 : we need to create 2nd window & so on... till last 3 elements of an array
            ![STEP 3](../../notes-pics/15-1-lecture/love-babbar/lecture-15-37.png)
            ![STEP 3](../../notes-pics/15-1-lecture/love-babbar/lecture-15-38.png)
            - so here `bad--` means we're removing the bad element & `bad++` means we're adding a new element
            - & then we updated the answer like this `ans = min(ans, bad)` & then return it 
            - here we're don't need to think about `<=k` , we just need to take care of `>` greater than
    - different approach + logic explanation 👍
        - we're using different approach where we can solve through only 1 for loop with single traversing
        ![explanation](../../notes-pics/15-1-lecture/love-babbar/lecture-15-39.png)
        - why we did `j = count`
            ----- explain this in exaceldraw
        

- `Notes ✅`: what kind-of questions can be formed on array : 
    - related to maths , how to find whether that question using kadane's algo or not , searching , sorting , bit manipulation , 2D array , sliding window , etc...
    - https://www.geeksforgeeks.org/largest-sum-contiguous-subarray

- `tip to make notes` : clear 3 things
    - what , how & why for that topic

- `advice` : for learning 
    - always go from small to big OR basics to advance
    - learn the basic stuff which required to learn that advance things , don't jump to directly on advance stuff

- after doing all those questions , then we're done with 25+ questions on array