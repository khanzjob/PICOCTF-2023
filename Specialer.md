# Specialer

## Challenge Info 

Tags: General Skills, bash, ssh 

AUTHOR: LT 'SYREAL' JONES, ET AL.

Points: 400

## Description
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.

## Solution 

In this shell, some of the commands are not available like ls, cat, more, less, bat, exa, etc. So it is difficult to operate. "echo" is working, so we can use ``` echo * ``` to see the available contents in the present directory. 
There are 3 directories - abra, ala and sim. So let's check out each directory. 

<img width="135" alt="image" src="https://user-images.githubusercontent.com/66155978/226010102-9fc1eb53-fe6a-415c-8cf4-0867a2a078e8.png"> <img width="108" alt="image" src="https://user-images.githubusercontent.com/66155978/226010821-690aa59c-22ec-44eb-92c1-48279aae5f8d.png">

So all 3 directories contains 2 text file each, the flag may be hidden in one of those. Now cat or its common alternatives are not available, so again we will be using echo to read the files. 

``` echo "$(<filename.txt)" ```

<img width="384" alt="image" src="https://user-images.githubusercontent.com/66155978/226012078-784ac02c-2a91-4b74-8bc2-9b8dc9946649.png">

Yayyy!!! We got our flag it was in /ala/mode.txt. 

Was the challenge worth 400 points 👀
## Flag 

picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_49193632}
