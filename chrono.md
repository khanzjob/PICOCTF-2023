# chrono

## Challenge Info 

Tags: General Skills, Linux

AUTHOR: MUBARAK MIKAIL

Points: 100

## Description

How to automate tasks to run at intervals on linux servers?
Use ssh to connect to this server:
Server: saturn.picoctf.net
Port: 64723
Username: picoplayer 
Password: tPmsUpiHeZ

## Solution 

Crontab is used to automate the tasks at intervals in Linux. SSH in the server and just read crontab to get the flag  

`cat /etc/crontab`

<img width="231" alt="image" src="https://user-images.githubusercontent.com/66155978/225908254-38720fcf-a441-4c89-a018-46f9301e2ecf.png">


## Flag 

picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}
