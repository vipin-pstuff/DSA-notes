# functions in cpp

## lecture 6 - love babbar (paid course)

- about function & why we return the value from a function
    ![functions & why we return the value from a function](../../notes-pics/14-lecture/love-babbar/lecture-14-0.png)

- why we use function 
    - avoid repetition
    - reuse
    - modular approach / code clean
    - save time
    - maintainability
    - easy to understand
    - easy testing
    - remove redundancy
    - readability
    ![why we use function](../../notes-pics/14-lecture/love-babbar/lecture-14-1.png)

- what is modular approach means in function
    - means different task we separated into their own function <br>
        & then we combine them into one function like a component in reactjs 
    - due to this readability increased

- what is function call stack 💡
    - before knowing about it , first know about what is stack data structure 💡💡💡
        - let's take example of shaadi in order to understand stack ,
        - now there're many plates like this  
            ![what is stack](../../notes-pics/14-lecture/love-babbar/lecture-14-2.png)
        - now when you take the plate , then first plate you'll pick i.e 4th one
        - so when plates were inserted like this first 1 then 2 then 3 , 4 , 5 <br>
            & when you extract/take then first plate will come 4 , 3 , 2 then 1 <br>
            so in stack that last one will be picked/extracted first i.e called LIFO (last in first out) orderly like this
            ![what is stack](../../notes-pics/14-lecture/love-babbar/lecture-14-3.png)
    - how function call stack works 
        ```cpp
        void printNumber() {
            cout << "Haaaa";
        }

        int main() {
            printNumber()
        }
        ```
        - so we have the stack already i.e function call stack & inside of it , first main() function will be created inside of it 
        - now main() function is calling printNumber() function , so on top of the main() function <br>
            printNumber() function will be created like this 
            ![what is stack](../../notes-pics/14-lecture/love-babbar/lecture-14-4.png)
        - now control will go inside printNumber() function body , now this function is just printing <br>
            so we'll get the message as a output 
        - now that ending curly braces of printNumber() function hit , then means printNumber() function is over <br>
            so printNumber() function will be pop out from function call stack 💡💡💡
        - now control goes inside main() function & the movement curly braces of main() function hit <br>
            then main() function will also pop out from the function call stack , now code is over

- why we need arguments & parameters in a function - understanding it via analogy example  
    - Let' say we want to say function that print sum of 5 numbers <br>
        then we need to send/gave that 5 numbers , then that function able to give sum 
    - & how that function will give the result , it'll give the output via `return` statement
    - parameters are like input arguments , just like props concept in reactjs

- pass by value & pass by reference ✅
    - pass by value
    

## lecture 11 - kunal kushwaha YT

- in programming , there's a DRY concept , so that's why use functions 
    ![functions](../../notes-pics/14-lecture/kunal-kushwaha/lecture-14-0.png)
- in C++ & java , whatever the return type of that function has , we'll return that return type from that function also
    - means if you're function has return type is int , then we should return only integer value also , not other datatype value 

