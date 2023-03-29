# MSB

## Challenge Info 

Tags: Forensics , Steganographu 
AUTHOR: LT 'SYREAL' JONES

## Description
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...

![Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada flag (1)](https://user-images.githubusercontent.com/66155978/227915378-5cbd8697-2aaa-4804-9ddb-fe2b4e06505a.png)

## Solution 

At first I tried binwalk but it didn't worked. Then I moved to StegSolve as in some previous CTFs I encountered the similar challenges and solved using stegsolve. 

So Let's open the image in stegsolve. Alpha planes didn't gave anything. After trying different bit planes combination, the flag was finally visible in RBG plane 7. 

<img width="959" alt="image" src="https://user-images.githubusercontent.com/66155978/227914791-89a9ca8b-d787-4124-8f9e-ef1006bba375.png">


## Flag

picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_572ad5fe}
