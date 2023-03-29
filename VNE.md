# VNE

## Challenge Info 

Tags: Binary exploitation, bash, env, injection 

AUTHOR: JUNIAS BONOU

Points: 200

## Description
We've got a binary that can list directories as root, try it out !!
ssh to saturn.picoctf.net:59803, and run the binary named "bin" once connected. Login as ctf-player with the password, af86add3

## Solution 

This is a simple one. There is one binary called "bin" which can read the directories with root permissions. Initially, I ran bin but it said 

"Error: SECRET_DIR environment variable is not set" 

So I set the environment variable to read the /root directort using 

``` 
export SECRET_DIR=/root
```
Now running bin lists the content of root directory. 

<img width="310" alt="image" src="https://user-images.githubusercontent.com/66155978/226422885-43a1c2c5-2328-4c64-989f-b4a252b35dca.png">

So now how to read the flag ?? . Hint says to modify the variable and add some more command to ls. So I modified the environment variable to list the directpry as well as read the contents of the file.

<img width="557" alt="image" src="https://user-images.githubusercontent.com/66155978/226423229-528cceb9-387e-428f-a7bb-4802813fa75c.png">


## Flag

picoCTF{Power_t0_man!pul4t3_3nv_1ac0e5a3}

