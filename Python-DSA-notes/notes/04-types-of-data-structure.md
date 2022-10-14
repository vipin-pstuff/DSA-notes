# Types of Data Structure

- 2 types of data structure 
    - `1` : Physical data structures
    - `2` : Logical data structures

## Lecture - abdul bari sir

- Physical Data Structures
    - Eg : array & linked list are two physical DS
        ![physical DS](../notes-pics/04-lecture/lecture-4-1.png)
        - & we can have more data structures of combination/variations of those two
        - Why we're calling them as Physical ? 💡
            - because those data structures decides/defines how the memories organize
            - means how the memories is allocated
        - & these two data structures are inbuilt/directly supported by C++ , Java , python 
    - Eg : Array data structure 
        - those complete single block is a contiguous memory locations
        - means if we have an array for 7 integers then all those 7 integers are together at one place
        - & that array have fixed size , once it's created of some size <br>
            then that size can't be increase or decrease . So size of an array is static 💡💡💡
        - that array can be created inside the stack or inside the heap memory (with the pointer variable inside stack) like this <br> 
            ![physical DS](../notes-pics/04-lecture/lecture-4-2.png)
        - When to use Array data structure ? ✅
            - use it when you're sure about what's the maximum number of elements that you're going to store
            - means if you know the length/size of the list then you can use array 
    - Eg : linked list data structure 
        - it's completely dynamic data structure & it's a collection of nodes <br>
            where each node contains data & link to next node
        - the length of the list in linked list data structure , can grow & reduce dynamically so it's having variable length
        - so as per your requirement , you can go on adding more & more nodes <br>
            & add more elements or you can reduce the size
        - the linked list data structure is always created inside the heap memory 💡💡💡 <br>
            & head -> will be the pointer variable (inside the stack memory) which will point that linked list
            ![physical DS](../notes-pics/04-lecture/lecture-4-3.png)
        - when to use Linkedin list data structure ? ✅
            - use it when we don't know the size of the list 
    - & these two comes in physical because they tell how the memory should be organized for storing the elements/data  <br>
        so they're more related to memory 💡💡💡

- Logical Data structures 
    - logical data structures are : <br>
        ![logical data structures](../notes-pics/04-lecture/lecture-4-4.png)
        - different b/w physical & logical data structures ✅
            - Physical Data structures : are actually meant for storing the data in the memory , means they'll hold the data 
            - Eg : when you have the list/array then you'll perform operations like inserting more values , <br>
                deleting existing values or searching for the values & many more operations
            - now question is how you want to utilize those values <br>
                means how you'll be performing insertion & deletion means what discipline you'll follow
            - that discipline is defined by those logical data structures 💡💡💡
        
    - types of data structures in logical DS : `Linear DS` , `Non-Linear DS` , `linear or Tabular DS`
        - Examples are : <br>
            ![](../notes-pics/04-lecture/lecture-4-5.png)
        - `stack` works on LIFO (last in first out) <br>
            `queues` works on FIFO (first in first out) <br>
            `trees` is non-leaner DS , so it'll be organized like a hierarchy <br>
            `Graph` is a collection of nodes & the links b/w the nodes <br>
            `Hash table` is a like table 
        - so these logical data structures are actually used in applications , used in algorithms <br>
            & for implementing these logical data structures , we use either array or linked list or combination of both <br>
            or any inbuilt Data structure 💡💡💡
        - means logical data structures are implemented via those different physical data structures 💡💡💡

## Lecture - Neso Academy

- 4 lecture - types of data structure 

- other reference YT : https://www.youtube.com/watch?v=w4LkuBGzPzs
