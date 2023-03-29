# Ready Gladiator 1

## Challenge Info 

Tags: Reverse Engineering, CoreWars

## Description 

Can you make a CoreWars warrior that wins?
Your opponent is the Imp. The source is available here. If you wanted to pit the Imp against himself, you could download the Imp and connect to the CoreWars server like this:
nc saturn.picoctf.net 60686 < imp.red
To get the flag, you must beat the Imp at least once out of the many rounds.

## Hint 

You may be able to find a viable warrior in beginner docs


## Solution 

In the part 1, the condition was to make Warrior 1 lose. In this challenge we need to make Warrior 1 win at least once. 

<img width="334" alt="image" src="https://user-images.githubusercontent.com/66155978/226113403-9247e5d5-79c8-454e-bf41-d1f10c39c3d6.png">

Let's go through the [refered doc](https://vyznev.net/corewar/guide.html) in the hint and see if anything's there. 

There's a instructions modifiers code given maybe we can use that. 

<img width="716" alt="image" src="https://user-images.githubusercontent.com/66155978/226118392-a1013c96-eb0c-4189-be3a-6c54a0df7c06.png">

Let's edit our imp.red file and then try to retreive our flag. 

<img width="294" alt="image" src="https://user-images.githubusercontent.com/66155978/226118460-71f5ce72-d720-4182-8648-d50b73aca236.png">



## Flag

picoCTF{1mp_1n_7h3_cr055h41r5_b9bb3269}
