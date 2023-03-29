# Permissions

## Challenge Info 
Tags: General Skills, vim

AUTHOR: GEOFFREY NJOGU

## Description

Can you read files in the root file?

The system admin has provisioned an account for you on the main server:

ssh -p 64078 picoplayer@saturn.picoctf.net

Password: x+T6aPgE4-

Can you login and read the root file?

## Solution 

1. Login using ssh creds as "picoplayer" user. 
2. Initially I thought the flag will be present in root directory and the permissions were denied for "picoplayer" , but there's another folder named "Challenge"
which contains the flaf inside the JSON file. 

<img width="784" alt="image" src="https://user-images.githubusercontent.com/66155978/225594743-cf94ae95-afbd-455e-a304-29cb493f378a.png">


## Flag

picoCTF{uS1ng_v1m_3dit0r_f6ad392b}
