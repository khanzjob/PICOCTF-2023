# Ready Gladiator 0

## Challenge Info 
Tags: Reverse Engineering, CoreWars

AUTHOR: LT 'SYREAL' JONES

Point: 100

## Description 

Can you make a CoreWars warrior that always loses, no ties?
Your opponent is the Imp. The source is available here. If you wanted to pit the Imp against himself, you could download the Imp and connect to the CoreWars server like this:

nc saturn.picoctf.net 56066 < imp.red

## Hints 

1. CoreWars is a well-established game with a lot of docs and strategy
2. Experiment with input to the CoreWars handler or create a self-defeating bot


## Solution 
In a round of Core War, two programs attempt to halt each other by overwriting instructions that are about to be executed. In the given source code there are two warriors playing and all the matches are getting tied. 

;redcode

;name Imp Ex

;assert 1

mov 0, 1

end

This RedCode program copies the value in memory location 0 to memory location 1 and then ends. I had no idea how to solve this so I just changed "mov" instruction and I got the flag. :D


<img width="406" alt="image" src="https://user-images.githubusercontent.com/66155978/225910184-a44cd7bb-25ec-466e-a3f5-7e85a14dc44b.png">


## Flag 

picoCTF{h3r0_t0_z3r0_4m1r1gh7_be33d1f6}

