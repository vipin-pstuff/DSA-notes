# basic Stuff of programming 

## lecture 2 - Love babbar course purchased

- `datatype` : 
    - for more about memory space : https://www.tutorialspoint.com/computer_fundamentals/computer_memory_units.htm
    - size of `int` datatype depends on compiler but generally we take 4bytes
        - & `1 byte = 8 bits` , here `bits means O or 1` 💡💡💡
        - so in memory , `int` datatype will be created 4 bytes like this 
            ![how an integer value will be stored](../../notes-pics/09-lecture/lecture-9-0.png)
            ![another example](../../notes-pics/09-lecture/lecture-9-0-0.png)
            - `Note ✅` : this is just for positive numbers which will be store in the memory in that way which is shown in picture
    - `int` datatype can store positive as well as negative values (whether it's a simple number or a fraction number)
    - `bool` datatype means boolean datatype 
        - it only represent either true or false to check whether that condition is true or false
        - so when we write the condition inside the if statement & in other condition syntax <br>
            then behind the scene that condition gets converted into true or false 💡💡💡
        - `0` -> means false & `1` means true 💡💡💡
        - size of the boolean datatype is `1byte` , not 1bit
    - `float` datatype 
        - it only store decimal/point value 
        - size is 4 bytes 
    - `double` datatype 
        - only store decimal/point value
        - size is 8 bytes <br>
            in memory it'll take 8 bytes & 1 bytes = 8 bits , so total 64 bits like this
            ![how an integer value will be stored](../../notes-pics/09-lecture/lecture-9-1.png)
        - difference b/w float & double are 
            - `1` : size are different  
            - `2` : double datatype is more precise/accurate than float in order to store decimal numbers 💡💡💡 
    - `ch` datatype means character datatype 
        - size takes 1 byte
        - always use single quotes to store a litter or a character , don't use double quotes <br>
            but for string datatype we always use double quotes 💡💡💡

- `how negative(-ve) numbers are stored in memory` ? : (not important becuz not asked in interview ✌)
    - let's say we have `int x = -5` , so we'll see algo/flow/steps to know how negatives number stored in memory
    - `STEP 1` : skip the minus or negative sign from that negative number , so here we'll get `5`
    - `STEP 2` : convert that number into binary representation , so for 5 is 101
    - `STEP 3` : take 2's compliment
        - how to take 2's compliment : 
            - for taking 2's compliment , find 1's compliment then add `1`
                - example : `STEP 1` : finding 1's compliment means flip all the bits 
                    - `STEP 1.1` & then do addition with that 1's compliment by `1` <br>
                        let's say we hav 1010 , so when we flip means keep opposite number 
                        ![how an integer value will be stored](../../notes-pics/09-lecture/lecture-9-2.png)
            - so in STEP 1 & 2 , we just took the example to understand
            - `STEP 1` : now that 101 which is stored in memory , convert it in 1's compliment in order to do 2's compliment 
                - so all those 0(zeroes) will become 1 like this & that 101 , it's bit will get flipped like this
                    ![how an integer value will be stored](../../notes-pics/09-lecture/lecture-9-3.png)
                - then add with 1 then we'll get this output 
                    ![how an integer value will be stored](../../notes-pics/09-lecture/lecture-9-4.png)
                    - & this is will be store in `-5`


    timeline : 50:09