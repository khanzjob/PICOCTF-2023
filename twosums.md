# two-sum 

## Challenge Info 

Tags: Binary exploitation, C, Make

Author: MUBARAK MIKAIL

Points: 100


## Description 

Can you solve this?
What two positive numbers can make this possible: n1 > n1 + n2 OR n2 > n1 + n2
Enter them here nc saturn.picoctf.net 63292. 

```Source
#include <stdio.h>
#include <stdlib.h>

static int addIntOvf(int result, int a, int b) {
    result = a + b;
    if(a > 0 && b > 0 && result < 0)
        return -1;
    if(a < 0 && b < 0 && result > 0)
        return -1;
    return 0;
}

int main() {
    int num1, num2, sum;
    FILE *flag;
    char c;

    printf("n1 > n1 + n2 OR n2 > n1 + n2 \n");
    fflush(stdout);
    printf("What two positive numbers can make this possible: \n");
    fflush(stdout);
    
    if (scanf("%d", &num1) && scanf("%d", &num2)) {
        printf("You entered %d and %d\n", num1, num2);
        fflush(stdout);
        sum = num1 + num2;
        if (addIntOvf(sum, num1, num2) == 0) {
            printf("No overflow\n");
            fflush(stdout);
            exit(0);
        } else if (addIntOvf(sum, num1, num2) == -1) {
            printf("You have an integer overflow\n");
            fflush(stdout);
        }

        if (num1 > 0 || num2 > 0) {
            flag = fopen("flag.txt","r");
            if(flag == NULL){
                printf("flag not found: please run this on the server\n");
                fflush(stdout);
                exit(0);
            }
            char buf[60];
            fgets(buf, 59, flag);
            printf("YOUR FLAG IS: %s\n", buf);
            fflush(stdout);
            exit(0);
        }
    }
    return 0;
}
```

## Hints

1. Integer Overflow 
2. Not necessarily a math problem 


## Solution 

The program asks for two positive values and checks the given condition. 

<img width="257" alt="image" src="https://user-images.githubusercontent.com/66155978/226161090-58e52a02-033d-472f-a2bf-ba732a2c4349.png">

Error says "no overflow" and also the hint says "integer overflow" so we need to occur a integer overflow here to get the flag. 

Integer overflow occurs when the result of the addition of two integers exceeds the maximum value that can be represented by the integer data type. 

In this program, integer overflow can occur if the sum of num1 and num2 is greater than the maximum value that can be represented by an int data type.

The maximum value that can be represented by a 32-bit signed int data type is 2,147,483,647. Therefore, if the sum of num1 and num2 is greater than 2,147,483,647, an integer overflow will occur.

<img width="330" alt="image" src="https://user-images.githubusercontent.com/66155978/226161175-62f6d6f6-096a-43bd-9916-88f3e80c6940.png">


## Flag

picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_76f333c8}
