# MatchTheRegex

## Challenge Info 
Tags: Web exploitation

AUTHOR: SUNDAY JACOB NWANYIM

Points: 100

## Description
How about trying to match a regular expression

## Solution 

There is a simple website which asks for a text and then matches with a correct input. 
The source code reveals the required regex pattern to input which will fetch the flag. 

<img width="313" alt="image" src="https://user-images.githubusercontent.com/66155978/225608844-0b4920f0-6712-44ef-899b-a75984b6ecb6.png">

^p.....F!? indicates that :

1. pattern matches only strings that start with the character "p".

2. "....." - Matches any five characters

3. "?" - Makes the preceding character or group optional. In this case, the ! character is made optional, 
which means that the pattern will match strings that end with either "F" or "F!".

So the obvious asnwer in this case could be picoCTF as it matches all the reuqirements. 😪😴

<img width="384" alt="image" src="https://user-images.githubusercontent.com/66155978/225608015-3c4c1888-81e0-4fdf-b2ee-ea04d626933a.png">

## Flag 

picoCTF{succ3ssfully_matchtheregex_9080e406}
