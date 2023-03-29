# Special

## Challenge Info 

Tags: General Skills, bash, ssh

AUTHOR: LT 'SYREAL' JONES

Points: 100


## Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. 
Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face.
When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.

ssh -p 61292 ctf-player@saturn.picoctf.net

The password is fd7746b4

## Solution

This is a weird shell... everything you type either changes capitalisation or correct the spelling. So we need to bypass this functionality and get the flag. Also, we are not authorized to read files which we don't own ( root files). 

<img width="277" alt="image" src="https://user-images.githubusercontent.com/66155978/226282284-bd13f10f-d77c-4480-b699-777a6d438d96.png">

I referred to this [doc](https://pubs.opengroup.org/onlinepubs/009604499/utilities/xcu_chap02.html) and figured out that we can use double quotes, dollar symbols to execute the commands. 

<img width="647" alt="image" src="https://user-images.githubusercontent.com/66155978/226282736-7e952058-d012-4671-ae7c-9b602d741ae6.png">

Now the commands are working but we can't run every command due to low privielge. 

Later, I referred to this [article](https://jarv.org/posts/cat-without-cat/) which shows how to read with cat without cat and I came up with this. 

```
cat flag.txt | cat /home/ctf-player/*/*.txt
```

And flag is printed on the screennn!!!

<img width="265" alt="image" src="https://user-images.githubusercontent.com/66155978/227587514-83434bbf-2840-42b9-a5b6-b6ef11cf2e6b.png">


## Flag

picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}

