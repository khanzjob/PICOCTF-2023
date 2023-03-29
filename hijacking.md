# hijacking 


## Challenge Info

Tags: Binary exploitation, privilege_escalation

AUTHOR: THEONESTE BYAGUTANGAZA

Points: 200 

## Description
Getting root access can allow you to read the flag. Luckily there is a python file that you might like to play with.
Through Social engineering, we've got the credentials to use on the server. SSH is running on the server.

saturn.picoctf.net 59120

Username: picoctf

Password: EVf4z1Lz73

## Solution 

In the home/picoctf there is hidden python file "server.py" which basically makes a ping request but we can't run the file because we are not root. 
So according to the challenge description we need to become root. 

So we can use ```sudo -l``` to see what command and binaries the current user can use. 

<img width="607" alt="image" src="https://user-images.githubusercontent.com/66155978/226179037-5ddb2dfd-03c9-4274-a36d-eda7e9e2060d.png">

So, server.py is doing nothing special, so our only option is to use ```/usr/bin/vi``` which is enabled for all the users. Let's head to [gtfobins](https://gtfobins.github.io/gtfobins/vi/) and see how to escalate to root. 

<img width="627" alt="image" src="https://user-images.githubusercontent.com/66155978/226179134-50bdd0c1-ebbe-40cd-b85c-3bffb9f2994a.png">

Let's try getting root user with this command and read our flag. 

<img width="307" alt="image" src="https://user-images.githubusercontent.com/66155978/226179223-62c1840c-7bc8-42e1-9171-dcc666284847.png">


## Flag

picoCTF{pYth0nn_libraryH!j@CK!n9_5a7b5866}

