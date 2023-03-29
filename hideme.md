# hideme

## Challenge Info
Tags: Forensics, Steganography 

AUTHOR: GEOFFREY NJOGU

## Description

Every file gets a flag.
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye here.

![Challeene Image ](https://user-images.githubusercontent.com/66155978/225354632-37f9a1bf-aa58-4005-a54e-802cc5ce4e9b.png)

## Solution 

1. We have been given a image here. The challegnge tags indicated about the use steganogrpahy. My go to tool for .png file steg is binwalk. 
2. running "binwalk flag.png" shows that there is a folder called "secret" with "flag.png" file inside it. So, lets extract that. 
3. running "binwalk -e flag.png --run-as=root" extracts the folder. 

<img width="876" alt="image" src="https://user-images.githubusercontent.com/66155978/225357194-cdb68960-e853-4d50-9f53-0dc157d4acc7.png">

4. Directory named "secret" inside the extracted folder contains an image file with flag written on it. 

<img width="713" alt="image" src="https://user-images.githubusercontent.com/66155978/225357960-f3a95873-490e-485a-ad09-4a42961a9bd7.png">


## Flag 

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_7931435f}
