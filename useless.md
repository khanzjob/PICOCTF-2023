# useless

## Challenge Info 

Tags: General Skills, man

AUTHOR: LOIC SHEMA

Points: 100

## Description

There's an interesting script in the user's home directory
The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.
Hostname: saturn.picoctf.net
Port:     58140
Username: picoplayer
Password: password


## Solution 

The challenge is indeed useless😪😴
1. Login using ssh  
2. There's a script named "useless" which performs basic mathematical operations and at the end says to read manual 

<img width="365" alt="image" src="https://user-images.githubusercontent.com/66155978/225892816-2246cb08-25e0-49b2-a645-c156e70d7900.png">

3. Just read the manual of "useless" using "man useless" and get the flag at bottom. 

<img width="668" alt="image" src="https://user-images.githubusercontent.com/66155978/225893027-8b4b8aa6-c4d9-4f8f-b35d-e4832e0eff47.png">


## Flag 
picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6173}
