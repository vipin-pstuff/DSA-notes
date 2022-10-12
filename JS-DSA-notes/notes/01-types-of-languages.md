# Types of Languages

- reference : Kunal Khushwaha java DSA course

## Notes - types of languages  

- `why we need programming languages` : 
    - internally , computer store data in 0 & 1 (binary numbers)
        - further , we'll see later on about how binary numbers stored in the memory
        - & how to convert decimal numbers into binary numbers & etc...
    - so whenever we're executing instructions through programming languages <br>
        then means we're instructing/saying to the computer let's say do this , tell me the time , etc... <br>
        so in this execution , CPU & RAM used & we'll see later on how all these things work
    - so things become difficult to write all those instructions in 0 & 1 . That's why we have programming languages <br>
        which allow us to write programs/instructions to say the computer to execute/run/perform that task/program
    - so that's why we have programming languages in order to write human readable format <br>
        behind the scene , computer will translate those code/programs/instructions in 0 & 1 

- `types of languages` : 
    - `Procedural` : 
        - specifies a series of well-structured steps & procedures to compose/run a program <br>
            or we can say contains a systematic order of statements , functions & commands to complete a task
        - means doing a task step by step
        - Eg : Java , python , C++ follow this property of procedural  
    - `functional` : 
        - is like a module
        - writing a program only in pure functions i.e never modify variables , but only create new ones as an output
        - used in situations where we have to perform lots of different operations on the same set of data , like ML
        - Eg : let's say we have 10 files & each file we need to perform addition 
            - then we can't write code of "sum of two numbers" for each 10 files
            - so by using functional programming , we can define a boilerplate of that task 
            - so that we can perform same task again & again & even easier to catch errors <br>
                & in future we just need to change the function only not 
        - first class functions : 
            - means eg : 
                ```js
                let a = 10 , b = 20 ;
                let c = b
                ```
            - so here we can see that we re-used the value of `b` in `c` variable 
            - so same with function we can do like re-assigning function variable name <br>
                to the other function . that means first class functions
        - Eg : this functional programming property followed by JS , python
    - `Object Oriented` : 
        - means resolves around objects
        - Code + Data = object
        - Eg : `when we say that data is a object datatype` : 
            - just create a collection of data which contain all the addresses of people <br>
                so type of this data will be string or paragraph. so here we're storing single data of same datatype
            - but create a collection of all the students where each student has 3 properties like name , roll no , marks <br>
                now what'll be the datatype of each student of which type . 
            - So we can't say one single datatype like string or integer because we're storing multiple/collection of datatypes <br>
                so one single datatype of that data i.e student . so it's datatype will be a custom datatype <br>
                which we can specify by using classes
            - so that collection of all will be called classes & instance of the class is called an object/instance
            - Eg : of class & object 
                - every humans is a class of Human & every humans is a object/instance of that Human class <br>
                - means a class is like a template/property like humans has two eyes , two ears , etc <br>
                    which is a property or template
                - so by using this template , God has created many objects means these are actual objects in the RAM <br>
                    so when we say `a = 10` then here `a` is a variable `10` is actually a object <br> 
                    which is inside real thing in the memory ✅
        - OOPS just a another programming paradigm which is used to divide all the code in different chunks <br> 
            to make easy for programmer to develop , debug , reuse & maintain software
            - Eg : OOPS
                - we have a car & it has properties like color , car category , engine type 
                - now let's say you want to change the type of the engine like from diesel to petrol or vice versa <br>
                    or from fuel to electrical . so if we change a particular thing then the entire car will get change 
                - means when we go to car mechanic & you want to change the engine  then think will that car mechanic <br>
                    will change the entire car or the particular part . so it'll change the particular part
                - so same thing like if we divide the code of the application into different parts <br>
                    like engine has separate code base & same thing for different parts <br>
                    & if we want to change the thing of that application then change the part of the program ✅
        - it's developed to make it easier to develop , debug , reuse & maintain software

- C++ , Java , JS , python supports all these ways of programming 

## Static VS Dynamic languages

- Eg : let's say we have 
    ```js
    let name = "Teen" // datatype will be string
    let rollno = 56 // datatype will be integer or number
    let marks = 47.8 // datatype will be decimal or float
    ```
    - now how do we & how does a programming language know what is the datatype of these variables
    - so we have the two ways i.e static & dynamic 

- `compile time (in static Vs Dynamic language)` : 
    - means as we know that we wrote the program in programming languages <br>
        & computer will compile/interpret that thing into machine code (0s & 1s) . so that computer can understand that 
    - so this conversion is known as compilation ✅ 
    - means source code gets converted into machine code . so this is known as compilation of the program

- `runtime` : 
    - means the program is running after compilation 
    - means when once the program/source code is converted into machine code <br> 
        & that machine code is running i.e where runtime things happens ✅

- Eg : `of datatype checking in Static Vs Dynamic language ✅` : 
    - example - of datatype checking  
        - in Dynamic language
            ```js
            let a = 10
            const name = "Teen Gen"
            ```
            - here we're not defining the datatype . so when this complete source code gets <br>
                compiled into machine code then the JS (Dynamic language) will think about 
            - so here we don't need to define the datatype of that variable while writing the source code 
        - in static language
            ```cpp
            int a = 10
            ```
            - here we define the datatype of the variable while writing the code . so CPP is the static language
            - so here while the program is compiling <br>
                means while the computer is converting your source code into machine code) <br>
            - so during this conversion time , the static programming language should know <br>
                what is the datatype of `a` variable ✅
            - so here datatype checking will done during compile time only
    - example - of how error comes 
        - in static language
            ```cpp
            int a = "Kunal"
            ```
            - here we'll get error because during your source code is compiling <br>
                computer will say you define this `a` variable as integer but value is in string
            - so we'll get error in compile time
            ```cpp
            int a = 10
            a = "Yaa"
            ```
            - we'll get an error because at compilation time , we define `a` as integer <br>
                but then we're assigning string value to `a` variable
            - but we can actually do this 
                ```cpp
                int a = 10 
                a = 89
                ``` 
            ```cpp
            'a' + 10
            ```
            - here we're adding a string with an integer , so we'll get an error 
        - in dynamic language
            ```js
            let a = 10
            a = "Yaa"
            ```
            - previously `a` was integer , now it's string
            - so here we'll not get error because in dynamic language , at compile time doesn't care about datatype 
            - so we can change datatype of the variable at compile time <br>
                so `a` variable was pointing to `10` , now `a` variable is pointing to `"Yaa"` ✅

<table>
<tr><td width="400px">

### Static languages

- perform datatype checking at compile time
- errors will show at compile time
- declare datatype before you use it 
- more control

</td><td width="400px">

### Dynamic languages

- perform datatype checking at runtime
- errors might not show till program is run
- no need to declare datatype of variables
- save time in writing code but might give error at runtime

</td></tr>
</table>

## compiler vs interpreter 

- for more : https://techprogramiz.blogspot.com/2020/03/translator-and-compiler-vs-interpreter.html

<table>
<tr><td width="400px">

### compiler

- `input` : it takes entire program as input at a time
- `output` : Intermediate Object code is generated
- `speed` : it execute conditional control statements fast
- `memory` : more memory is required. Due to the creation of object code 
- `need compile` : program need not to be compiled every time
- `error` : it display error after entire program is checked
- `Example` : C , C++ , typescript
- `Error detection` : difficult

</td><td width="400px">

### interpreter 

- `input` : it takes single instruction as input at a time
- `output` : No Intermediate Object code is generated
- `speed` : it execute conditional control statements slower than compiler
- `memory` : less memory is required. It doesn't create intermediate object code 
- `need compile` : every time higher level program is converted into lower level program
- `error` : it display error after each instruction interpreted & stopped in that line of code only & further code will not be executed until error didn't removed 
- `Example` : JS , python
- `Error detection` : easier comparatively

</td></tr>
</table>

