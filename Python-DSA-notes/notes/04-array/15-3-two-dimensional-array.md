# Two Dimensional Array

## lecture 10 - love babbar (paid course) - 2D array

- what is 2D array & why we need it 
    - what is 2D array 
        ![what is 2D array](../../notes-pics/15-3-lecture/love-babbar/lecture-15-3-0.png)
    - why we need 2D array instead of 1D array
        - right now we just made matrix of `3 row X 3 column`  
        - now let's say , we need 1000 rows & 1000 columns , so will you write code 1000 times <br> 
            so here we can use 2D array

- how to visualize 2D array or matrix in 1D array
    - so if we do via combination of 1D array then becomes difficult to visualize <br>
        so actually we want that , we solved the question in 2D array & behind the scene things done in 1D array
    - so we can do `int arr[5][10];` means `[5]` is row & `[10]` is column , <br>
        `Notes ✅` : first we access row & then column 💡💡💡 , rows are in horizontal & columns are vertical 💡💡💡<br>
        so we created 2D array based on this one line of code
    - `Ques` : make 1000 rows & 1000 columns
        - ans : `int arr[1000][1000];`
    - index will start from `0` whether it's a row or a column , same as we're doing in pattern question like this
        ![how indexing starting in matrix or in 2D array](../../notes-pics/15-3-lecture/love-babbar/lecture-15-3-1.png)
        ![how to show that block of matrix or of 2D array](../../notes-pics/15-3-lecture/love-babbar/lecture-15-3-2.png)
        
- while doing code , we'll see these points
    - creation of 2D array or matrix 
    - how to access a block of 2D array or matrix 
    - create a function for simple 2D operation

- how 2D array is stored in memory 
    - in memory , there's are blocks in linear or continuous stream of block , it's not like this <br>
        ![we can't show the 2D array in memory like this](../../notes-pics/15-3-lecture/love-babbar/lecture-15-3-3.png)
    - `imp Note 🔥` : when we do `arr[1][2]` in 2D array , 
        - then how `arr[1][2]` is translated & mapping with 1D array behind the scene
        ![when 2D array converted into 1D array , then how index mapping works](../../notes-pics/15-3-lecture/love-babbar/lecture-15-3-4.png)






