# binary search algo

- questions on binary search
    ![questions on binary search](../../notes-pics/16-1-lecture/love-babbar/lecture-16-1-0.png)

## lecture - love babbar (paid course)

- why we need binary search algo ✅
    - in linear search
        - time complexity of linear search i.e `O(n)`
        - when we have an 1D or linear array , then we traverse on each element one by one <br> 
            so where we're doing single traversal
    - time complexity of binary search is `O(log n)` then what `O(log n)` means & why we need binary search 💡💡💡
        ![questions on binary search](../../notes-pics/16-1-lecture/love-babbar/lecture-16-1-1.png)
        - so when we're using binary search on the array which has size i.e `2^100` <br>
            then we just need to do 100 comparison which is optimized instead of using linear search
    - so due to binary search algo , we save tons of computation time & due to this we have the processing power 💡💡💡
- limitation or condition where we can use binary search & where we can't use it 💡💡💡
    - either you're using array or vector or any data structure <br>
        like in array , each elements/data should be either in increasing/ascending order or decreasing/descending order <br>
        means each data inside any data structure (like array) should be <br>
        in sorted order (either ascending or descending order) then we can apply binary search
    - so we can say that binary search can be applied only on monotonic/monotonous function <br>
        `monotonic` means either data inside an array are in ascending order or descending order
    - Eg : inside an array , if the data is random order then we can't apply binary search algo on that array 💡💡💡

- understanding binary search algo
    - Example : 
        - we have given input i.e `[3, 5, 7, 9, 11, 15, 18]` which is in increasing order
        - we need to find out target i.e `15` , so whether 15 is present in this array or not
    - approach
        - `1st approach` : if we don't know binary search algo , then we'll use linear search algo
            - so we need to check & compare each element of an array
            - so in linear search algo , time complexity will be `O(n)`
        - `2nd approach` : we have an array which is already in increasing order
            - so we'll use binary search because we can take the advantage of given input array <br>
                which is already in increasing order
            - `STEP 1` : so inside that array , starting value is considered as start & ending value is will be as end
    


