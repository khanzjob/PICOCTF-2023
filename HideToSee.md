# HideToSee

## Challenge Info 
Tags: Cryptography

AUTHOR: SUNDAY JACOB NWANYIM

## Description
How about some hide and seek heh?
Look at this image here.

![atbash](https://user-images.githubusercontent.com/66155978/225324999-37283404-2d11-446f-9ac9-97d6b5a1945d.jpg)

## Hint 
Download the image and try to extract it.

## Solution

1. The challenge name "HideToSee" gives an idea that steganogrpahy might have been used here. So we can use "steghide" to extract the hidden data. 
2. Using steghide without any passphrase gives the hidden file "encrypted.txt" 

<img width="257" alt="image" src="https://user-images.githubusercontent.com/66155978/225331302-36e82eb1-e23b-43c2-8dd9-9094db3cb51c.png">


3. The text file contains a encrypted code which is most probably atbash cipher. Use www.dcode.fr/atbash-cipher to decode the Atbash cipher and find the flag. 


## Flag
picoCTF{atbash_crack_61996088}
