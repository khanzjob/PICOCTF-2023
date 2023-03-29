# FindandOpen 


## Challenge Info 

Tags: Firensics 

AUTHOR: MUBARAK MIKAIL

Points: 200 

## Description 

Someone might have hidden the password in the trace file.
Find the key to unlock this file. This tracefile might be good to analyze.

## Hints 

1. Download the pcap and look for the password or flag.
2. Don't try to use a password cracking tool, there are easier ways here.


## Solution 

Here we have a password protected zip file and a pcap file which probably contains the password. 

So again a pcap file and again there were codes like previous challenge "pcapPoisoning" . So I straight went up to use strings and found this  

<img width="292" alt="image" src="https://user-images.githubusercontent.com/66155978/226177940-53b2c799-0132-4e63-a9cc-0ae963c5cb13.png">

![image](https://user-images.githubusercontent.com/66155978/226177954-154611b4-cacf-460d-acfd-2dd0016d0eb9.png)

I used base64 to decode the string 

<img width="399" alt="image" src="https://user-images.githubusercontent.com/66155978/226177976-05848f70-79b1-4fd4-b4f0-d788eba6bdf5.png">

Now initially I didn't find anything more... stuck for hours..trying to find rest of the  part of the flag... 

Then I noticed Hint 1 and my one friend suggested to use flag to find the flag... So I tried entering the decoded string and it worked 💥

<img width="307" alt="image" src="https://user-images.githubusercontent.com/66155978/226178212-939f77b9-d32e-466d-9d06-84d699de3794.png">


## Flags

picoCTF{R34DING_LOKd_fil56_succ3ss_5ed3a878}
