# babygame01 

## Challenge Info 

Tags: Binary Exploitation, game 

AUTHOR: PALASH OSWAL

Points: 100

## Description 

Get the flag and reach the exit.
Welcome to BabyGame! Navigate around the map and see what you can find! The game is available to download here. There is no source available, 
so you'll have to figure your way around the map. 

You can connect with it using nc saturn.picoctf.net 60352.

## Solution 

So its a game accessible by  w(to go up), a( to go left), s(to go down) , d (to go right). 

We need to reach at the end of the game with the flag which is at position 29,89 . 

<img width="278" alt="image" src="https://user-images.githubusercontent.com/66155978/226182947-7d163c80-f826-4d6b-849d-e55f41911c6a.png">


Reaching there is pretty easy just hit s and w till it reaches there. 

But we need flag too and you won't get flag just by reaching there... I scratched my head for hours, then I was just trying to go backwards like out of the game.

I pressed 'a' for 3-4 times and saw that there was a change in position "Player has flag". 

<img width="479" alt="image" src="https://user-images.githubusercontent.com/66155978/226182812-45d9b9fb-7a0d-4286-a9c1-4ae109779cbc.png">

Then while entering again in the game using "d" 64 changed to 46 

<img width="393" alt="image" src="https://user-images.githubusercontent.com/66155978/226182913-2ea482f8-f9e0-4bca-a4cb-cdd0d858013b.png">

Now I went to the end of the game again and this time flag was also prompted. 

<img width="469" alt="image" src="https://user-images.githubusercontent.com/66155978/226182983-ece94fd6-550d-4e19-be3a-873e30941362.png">


# Flag 

picoCTF{gamer_m0d3_enabled_fff873ca}
