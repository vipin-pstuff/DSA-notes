# Binary search algo problems

## lecture - love babbar (paid course)

- here we'll how to apply binary search algo in 2D array
- how do we know that what level of questions we have in binary search algo
    - `1st level` : classical questions (that you just did in 1D array)
        - if you understand those 10 questions then you completed the 1st level
    - `2nd level` : 2D array (we solve catchy questions)
    - `3rd level` : reduce search space (this concept is related to CP) & it contains questions like : 
        - book allocation 
        - Aggressive Cows <br> 
            https://leetcode.com/discuss/general-discussion/1302335/aggressive-cows-spoj-fully-explained-c
        - painter’s partition

- how to use binary search algo in 2D array
    - `ques` : find the target element in 2D array via binary search algo
        - understanding ✅
            ![conditions to use binary search algo in 2D array](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-0.png)
        - approach : we have 2 ways 
            - `1st way` : using linear search algo or brute force
                ![brute force approach or linear search algo](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-1.png)
            - `2nd way` : optimize approach i.e binary search algo
                - we already know those 2 conditions in order to apply binary search algo in 2D array <br>
                    but if the input question is not fulfilling those 2 conditions then we can't apply binary search algo in 2D array
                - so we can apply binary search algo in that 2D array input in 2 ways like this
                    ![applying binary search algo in both ways](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-2.png)
                - what will be the algo/steps
                    ![time complexity & algo steps](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-3.png)
            - how to find that row which contain the target value ? 👍
                ![approach explain : how to find that row which contain the target value](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-4.png)
                - conclusion <br> 
                    ![conclusion](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-5.png)
                    ![summary of those 5 conditions](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-6.png)
            - so we need to apply binary search algo 2 times
            - student's doubts
                - `1` : here in above approach , we're using 2 pointer approach , but i need 1 pointer approach
                    ![student doubts](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-7.png)
                - `2` : what if we apply binary search algo in each row inside 2D sorted array 
                    - then time complexity is number of rows * log of column i.e `O(n * logm)` 💡💡💡
                    - another approach to solve this question 
                        ![another approach](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-8.png)
                        - check this another approach solution on YT love babbar DSA course
        - DRY RUN
            ![DRY RUN - finding the row which contain the target value](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-9.png)
            ![DRY RUN - after finding that row , then finding the target value](../../notes-pics/16-2-lecture/love-babbar/lecture-16-2-10.png)
        - code
            - STEP 1 : creating search() function to find the row which contain the target element
                ```cpp
                #include <iostream>
                using namespace std;

                bool search(int arr[][3], int n, int m, int target) {
                    // find row 
                    int s = 0; // starting row
                    int e = n-1; // ending row

                    int mid = s + (e-s)/2; // we wrote this formula because integer overflow error will never come
                        // but if we use (s + e)/2 then there's a chance that inter overflow error will happen 💡💡💡

                    // here why we use <= instead of < 
                        // because it's already discussed in a previous lecture
                    while(s <= e) {
                        // check starting element of row
                        if (arr[mid][0] == target) {
                            cout << row << " " << 0 << endl;     // printing coordinates of that target element
                            return true ;
                        }

                        // check ending element of row
                        if (arr[mid][m-1] == target) { // here (m - 1) means last column
                            cout << row << " " << mid-1 << endl; // printing coordinates of that target element
                            return true;
                        }

                        // check if element is present in between starting & ending element 
                        if (target > arr[mid][0] && target < arr[mid][m-1]) {
                            
                            // apply binary search on column
                            bool ans = binarySearch(arr, n, m, mid, target);
                            return ans;
                        }

                        // CHECK upper part
                        if (target < arr[mid][0]) 
                            e = mid - 1;

                        // check lower part
                        if (target > arr[mid][m-1])
                            e = mid + 1;

                        mid = s + (e-s)/2;
                    }

                    return false;
                }

                int main() {
                    int arr[3][3] = {1, 5, 9, 14, 20, 23, 30, 34, 43};

                    int n = 3;
                    int m = 3;
                    int target = 34;
                    cout << search(arr, n, m, target);

                    return 0;
                }
                ```
            - STEP 2 : writing binary search algo to find the target element inside that row (which contain the target element)
                ```cpp
                #include <iostream>
                using namespace std;

                bool binarySearch(int arr[][3], int n, int m, int row, int target) {
                    int s = 0;
                    int e = m-1;

                    int mid = s + (e-s)/2;

                    while(s <= e) {
                        if (arr[row][mid] == target) {
                            cout << row << " " << mid << endl;
                            return true;
                        }

                        if (arr[row][mid] < target) {
                            s = mid + 1;
                        } else {
                            e = mid - 1;
                        }
                        mid = s + (e-s)/2;
                    }
                    return false;
                }

                // put code from STEP 1
                ```
            - STEP 3 : using DRY Concept 
                - here we can see that we use this line of code i.e `int mid = s + (e-s)/2;` 2 times <br>
                    it as a global variable inside binarySearch() function & inside while loop of binarySearch() function  
                - so we can put this line of code i.e `int mid = s + (e-s)/2;` inside only while loop <br>
                    then we don't need to define this `mid = s + (e-s)/2;` again
                ```cpp
                #include <iostream>
                using namespace std;

                bool binarySearch(int arr[][3], int n, int m, int row, int target) {
                    int s = 0;
                    int e = m-1;

                    while(s <= e) {
                        int mid = s + (e-s)/2;

                        if (arr[row][mid] == target) {
                            cout << row << " " << mid << endl;
                            return true;
                        }

                        if (arr[row][mid] < target) {
                            s = mid + 1;
                        } else {
                            e = mid - 1;
                        }

                        // mid = s + (e-s)/2; 
                            // -- how we don't need to define this again 
                                // because we used define mid variable inside while loop itself
                            // but if you use previous way then it's more readable 
                    }
                    return false;
                }

                // put code from STEP 1
                ```

- advice to become better programmer
    - after finding the approach of a question then do DRY RUN 5 times with different test cases 🔥🔥🔥 <br>
        & to visualize more , you can print those variables also like this 
        ![visualize the code](../../notes-pics/16-2-lecture/love-babbar/how-to-visualize-the-code.png)
        - so this the basic debugging if you stuck in the code
    - this practice will help you to become better & you'll be able to visualize the code in better way 




