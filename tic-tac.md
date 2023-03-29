# tic-tac

## Challenge Info 

Tags: Binary Exploitation, bash, linux, toctou

AUTHOR: JUNIAS BONOU

Points: 200 

## Description 

Someone created a program to read text files; we think the program reads files with root privileges but apparently it only accepts to read files that are owned by the user running it.
ssh to saturn.picoctf.net:51906, and run the binary named "txtreader" once connected. 

Login as ctf-player with the password, fd7746b4

## Solution 

There is file "txtreader" which reads the files owned by current user. We need to read "flag.txt" but it is not owned by "ctf-player" so we can't. 

Tags refer to "toctou" which is a vulnerability related to RACE conditions. It occur when the attacker can modify the resources after the check but before the use. 

This [article](https://samsclass.info/127/proj/E10.htm) helped a lot in solving the challenge, I just followed the steps shown here with some modifications. 

1. Create a txt file with any content in it.
2. Making a Symbolic Link ``` ln -s NEWFILE flip ```
3. Overwriting the Symbolic Link ``` ln -sF flag.txt flip ```

<img width="314" alt="image" src="https://user-images.githubusercontent.com/66155978/226192687-bbd9ea0d-1919-4a7e-869e-4a8793e8cf41.png">


4. Testing Flipping Rate - To win the race, we need to flip the link during the vulnerable interval so we can flip the link many times and see how long it takes.

``` for i in {1..1000}; do ln -sf flag.txt flip; ln -sf NEWFILE flip; done ```

5. Starting Constant Flipping - 

```while true; do ln -sf secret flip; ln -sf public flip; done &```

This flips the link from "public" to "secret" rapidly, and runs in the background.

<img width="594" alt="image" src="https://user-images.githubusercontent.com/66155978/226192748-b0246bfb-639e-43fc-aec2-6d8452bb05b8.png">


In the case of articleflippinf 30 times worked, but in my case I need to flip it 200 times and then I got the flag. 


<img width="433" alt="image" src="https://user-images.githubusercontent.com/66155978/226193074-fce02d1a-f72d-4986-9cc1-493f83f5a4d6.png">



## Flag 

picoCTF{ToctoU_!s_3a5y_a5726c65}
