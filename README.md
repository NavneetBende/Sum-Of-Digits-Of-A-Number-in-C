# Sum-Of-Digits-Of-A-Number-in-C

C Program to Find Sum of Digits of a Number 
In this C program, we will code Sum of Digits of a Number in C we will allow the user to enter any number and then we will divide the number into individual digits and add those individuals (sum=sum+digit) digits using While Loop.

Ex:-  number is 231456

 2 + 3 + 1 + 4 + 5 + 6 = 21

Sum of digit of a given number is 21

sum of digits of a number in c
Sum of Digits in C Program
Working:-
For user input num

Initialize sum = 0
Extract the last digit of the number and add it to the sum (sum += num % 10)
 Reduce the number  (num = num / 10
Keep doing this until num becomes 0
Sum Of Digits Of A Number in C
Method 1
Uses the iterative way of calculation

C Code
Run

// Write a Program to Find Sum of Digits of a given number
#include<stdio.h>

int main ()
{
    int num, sum = 0;
 
    num = 1234;
    printf("The number is = %d\n",num);

    //loop to find sum of digits
    while(num!=0){
        sum += num % 10;
        num = num / 10;
    }
 
    //output
    printf("Sum: %d\n",sum);
 
    return 0;

}
// Time complexity : O(N)
// Space complexity : O(1)
Output
The number is = 1234
Sum: 10

Related Pages
Program to check Prime Number

Program to print Prime Number in range

Program to reverse a number

Program to check palindrome or not

Program to check armstrong number or not

While loop in C
Method 2
This method uses a recursive approach in C

Code
Run

// Time complexity : O(N)
// Space complexity : O(1)
// Auxiliary Space Complexity : O(N)
// Due to function call stack
#include<stdio.h>

int getSum(int num, int sum){
    
    if(num == 0)
        return sum;

    sum += num % 10;

    return getSum(num/10, sum);
}
int main ()
{
    int num, sum = 0;
    num = 6789;
    printf("The number is: %d\n",num);   
    printf("Sum: %d\n",getSum(num, sum));
 
    return 0;

}
// Time complexity : O(N)
// Space complexity : O(1)
// Auxilary space complexity O(N)
Output
The number is = 6789
Sum: 30
While loop in C
Method 3
The above recursive method can also be reduced down to something like this below -. Note this method also uses a recursive approach in C

Code
Run
// Time complexity : O(N)
// Space complexity : O(1)
// Auxiliary Space Complexity : O(N)
// Due to function call stack
#include<stdio.h>
 
int getSum(int num)
{
    if(num == 0){
        return 0 ;
    }
    
    int digit = num % 10;
    
    return digit + getSum(num / 10) ;
}
 
int main()
{
    int num = 2545;
    printf("Sum: %d", getSum(num));
    return 0;
}
Output
Sum: 16
Method 4
We can also take numbers as input in char array/string format.

The below program uses this approach. You must have knowledge of the Ascii Table.

Please check ASCII Table here

Note
The below method also solves the issue of large numbers. Long long also cant store numbers larger than in the range of > 1019.
Code
Run

// Time Complexity : O(N)
// Space Complexity : O(1)
#include<stdio.h>
#include<string.h>

int getSum(char str[], int len)
{
    int sum = 0;
 
    // Traverse through the whole string(char array)
    for (int i = 0; i < len; i++) 
    {
        // Ascii value pf numbers start from 48
        // subtracting 48 will give us value in int
        sum = sum + str[i] - 48;
    }
    return sum;
}
 
int main()
{
    char num[] = "987654321";
    int len = strlen(num);
    
    // can also use below
    // int len = sizeof(num)/sizeof(num[0]);
    
    printf("Sum: %d", getSum(num, len));
    return 0;
}
Output
Sum: 45
Method 5
Another method working with character input. You must have knowledge of the Ascii Table.

Please check ASCII Table here

Code
Run

#include<stdio.h> 
 
int main()
{
    int index = 0, sum = 0, temp;
    char num[1000];
   
    // taking character input for num
    printf("Input an integer: ");
    scanf("%s", num);
 
    // continue until we hit end of the char array 
    while (num[index] != '\0') 
    {
        // subtract ascii value of num from ascii value of '0'
        temp   = num[index] - '0';
        sum = sum + temp;
        index++;
    }
 
   printf("Sum of digits of %s is: %d ",num, sum);
 
   return 0;
}
Output
Input an integer: 12345
Sum of digits of 12345 is: 15 
