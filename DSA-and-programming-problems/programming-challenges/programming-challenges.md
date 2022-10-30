# Programming Challenges

## Basics 

- Q1 : WAP to calculate area of a circle. Take radius as an input from user
    ```py
    import math

    radius = float(input("enter the radius of a circle"))
    Area_Of_Circle = math.pi * pow(radius, 2)
    print(round(Area_Of_Circle,2))
    ```

- Q2 : WAP to calculate area of a rectangle. Take length & breadth from user
    ```py
    length = float(input("Enter the length of a rectangle"))
    breadth = float(input("Enter the breadth of a rectangle"))

    area_of_reactangle = length * breadth
    print(area_of_reactangle)
    ```

- Q3 : WAP to calculate volume of a cuboid. Take user input
    ```py
    length = float(input("Enter the length of a cuboid"))
    breadth = float(input("Enter the breadth of a cuboid"))
    height = float(input("Enter the height of a cuboid"))

    volume_of_cuboid = length * breadth * height
    print(volume_of_cuboid)
    ```

- Q4 : WAP to calculate simple interest. Take user input
    ```py
    principle_balance = float(input("Enter the principle"))
    annual_interest_rate = float(input("Enter the rate"))
    time = float(input("Enter the time (in years)"))

    simple_interest = (principle_balance * annual_interest_rate * time) / 100
    print("Simple Interest is : " , simple_interest)
    ```

- Q5 : WAP to calculate average of three numbers 
    ```py
    num1 = int(input("Enter the any 1st Integer number"))
    num2 = int(input("Enter the any 2nd Integer number"))
    num3 = int(input("Enter the any 3rd Integer number"))

    avg_of_three_numbers = (num1 + num2 + num3)/3
    print(round(avg_of_three_numbers, 1))
    ```

## Operators 

- WAP to swap values of two int variables
    ```py
    num1 = 5 
    num2 = 2 

    # swapping values of 2 variables each other with 3rd variable
    num3 = num1
    num1 = num2
    num2 = num3

    print("Value of num1 is : ", num1)
    print("Value of num2 is : ", num2)
    ```

- WAP to swap values of two int variables without using third variable
    ```py
    num1 = 5 
    num2 = 2 

    # swaping values of 2 variables together without 3rd variable  
    num1 = num1 + num2 
    num2 = num1 - num2
    num1 = num1 - num2

    print("num1 =", num1)
    print("num2 =", num2)
    ```

- WAP to get the individual digits from a integer number & print them (eg : 137 => 1,3,7)
    ```py
    num = 137

    newNum = str(num) # typecasting from integer to string

    for digit_num in newNum :
         print("Digit :" , digit_num)
    ```
    ```cpp
    #include <iostream>    
    using namespace std;

    int main() {
        int n = 137;
        // int n = -137; 
            // if we have negative number then we'll get each digit in negative also

        while(n != 0) {

            int digit = n%10; // this variable will be created/initialized in the memory from scratch as new variable 
                        // because we're created it inside the loop 💡💡💡
                // taking out the digit
                
            cout << "digit: " << digit << endl;
            n = n/10; // making the number small
        }

        cout << "DONE" << endl;
    }
    ```
    - Note : we can't solve this problem by using `%` modulus operator inside JS , python

- WAP to combine a number based on individual given digits & print it (eg : 1,3,4 => 134) 
    ```py
    digit_num1 = 1
    digit_num2 = 3
    digit_num3 = 7

    # this code is not effectice what if we have 10000 numbers
        # so individually , we can't put them manually 
        # so in that situation , we need to put each number inside an array
    new_num = f'{digit_num1}{digit_num2}{digit_num3}'

    print(new_num)
    ```

- WAP to print last digit of a given number
    ```py
    num = 137

    last_digit_num = num%10
    print(last_digit_num)
    ```

- WAP to print a given number but without last digit
    ```py
    import math

    num = 137

    # First way : 
    skip_last_digit_num = math.trunc(num/10)

    # second way :
    second_way = int(str(num)[:-1])

    print("Skipping last digit from a number :" , skip_last_digit_num)
    ```

- WAP to input a character from keyboard and print it's ASCII code
    ```py
    letter = input("Enter a character :")

    print(f'ASCII Code of {letter} is :', ord(letter))
    ```

- WAP to decimal to binary 
    - answer : https://www.geeksforgeeks.org/python-program-to-covert-decimal-to-binary-number/
    ```py

    ```

- WAP to binary to decimal
    - answer : https://www.scaler.com/topics/binary-to-decimal-in-python/
    ```py

    ```

## Output Question 

- variable scope MCQ : 
- pre & post increment & decrement MCQ
- break & continue with loop MCQ
- switch statement MCQ

## decision control

- WAP to check whether a given number is positive or non-positive
- WAP to check whether a given number is divisible by 5 or not 
- WAP to check whether a given number is even or odd
- WAP to check whether a given number is even or odd without using % operator
- WAP a program to check whether an year is a leap year or not 
- WAP to check whether a given number is positive , negative or zero
- WAP to find greater between two numbers
- WAP to find greater among three numbers
- WAP which takes marks of 5 subjects (assume maximum marks for each subject is 100)
    - Display result as pass or fail. Also print division obtained if candidate has passed the exam

## switch statement 

- Write a program which takes month number as an input & display number of days in that month
- write a menu driven program with following options :
    - a. addition
    - b. subtraction 
    - c. multiplication
    - d. division
    - e. exit
- write a program which takes day number of a week & display unique greeting message for the day
- write a menu driven program with following options : 
    - a. check whether a given set of three numbers are lengths of an isosceles triangle or not 
    - b. check whether a given set of three numbers are lengths of sides of a right angled triangle or not 
    - c. check whether a given set of three numbers are equilateral triangle or not 
    - d. Exit

## iterative control 

- Program to print digit pattern
- WAP to print first 10 natural numbers
- WAP to print first 10 natural numbers in reverse order
- WAP to print first **N** natural numbers
- WAP to print first **N** natural numbers in reverse order
- WAP to print first 10 even natural numbers
- WAP to print first 10 even natural numbers in reverse order
- WAP to print first 10 odd natural numbers
- WAP to print first 10 odd natural numbers in reverse order
- WAP to print first **N** odd natural numbers 
- WAP to print first **N** odd natural numbers in reverse order
- WAP to print squares of first N natural numbers
- WAP to calculate sum of first N natural numbers 

## loop

- WAP to calculate factorial of a number
- WAP to calculate sum of digits of a given number
- WAP to count digits in a given number
- WAP to reverse a number  
- WAP to print table of user's choice 
- WAP to check whether a given number is a term in fibonacci series or not  
- WAP to check whether a given number is prime or not 
- WAP to print all prime numbers under 100
- WAP to find Nth term of a fibonacci series
- WAP to calculate LCM of two numbers
- WAP to calculate GCD/HCF of two numbers
- WAP to print all factors of a given number
- WAP to print all prime factors of a given number 
- WAP to print all prime numbers between two given numbers
- WAP to calculate sum of squares of first **N** natural numbers
- WAP to calculate sum of cubes of first **N** natural numbers
- WAP to calculate sum of first **N** odd natural numbers
- WAP to print first **N** terms of a fibonacci series
- WAP to print next prime number of a given number
- WAP to check whether two given numbers are co-Prime or not 
- WAP to print first **N** prime numbers

## start pattern 

- Program to Print Floyd’s Triangle
- solid square pattern , hollow square
- https://www.faceprep.in/c/pattern-programs-in-c/
- https://www.geeksforgeeks.org/how-to-learn-pattern-printing-easily/
- 

## functions 

- write a function to calculate area of a circle (TSRS)
- write a function to print first **n** natural numbers (TSRS)
- write a function to print first **n** even natural numbers (TSRS)
- write a function to calculate sum of first **n** natural numbers (TSRS)
- write a function to calculate sum of squares of first **n** natural numbers (TSRS)
- write a function to check whether a given number is even or odd (TSRS) (Return 1 if even otherwise return 0)
- write a function to calculate factorial of a number (TSRS)
- write a function to calculate number of permutations which can be made from **n** items , selected **r** at a time (TSRS)
- write a function to calculate number of combinations which can be made from **n** items , selected **r** at a time (TSRS)
- write a function to check whether a given number is prime or not (TSRS) (Return 1 if prime , otherwise return 0)
- write a function to find next prime number of a give number (TSRS)
- write a function to print all prime numbers between two given numbers (TSRS)
- write a function to check whether a given number is an armstrong number or not 
- write a function to print all Armstrong numbers in the given range
- write a function to remove all occurrence of a given digit from a given number