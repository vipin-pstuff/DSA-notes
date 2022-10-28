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

- WAP a program to input a character from keyboard and print it's ASCII code
    ```py
    letter = input("Enter a character :")

    print(f'ASCII Code of {letter} is :', ord(letter))
    ```

## Output Question 

- variable scope MCQ : 
- pre & post increment & decrement MCQ
- break & continue with loop MCQ
- switch statement MCQ

## decision control

## iterative control 

- Program to print digit pattern


