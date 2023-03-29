# Java Code Analysis!?! 

## Challenge Info 

Tags:  Web Exploitation 

AUTHOR: NANDAN DESAI

Points: 300


## Description 

BookShelf Pico, my premium online book-reading service.
I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
Here are the credentials to get you started:

Username: "user"

Password: "user"

Source code can be downloaded here.
Website can be accessed here!.

## Solution 

So we have been given a credentials for user account which is a "free" account. THe website contains 3 books and "free" user can read only 1 book, while premium can where free, premium and Admin can read 1 book each. 

<img width="940" alt="image" src="https://user-images.githubusercontent.com/66155978/226203950-0282fdc1-2f55-44b4-a236-e9bec12c3264.png">


Now obviously we are not allowed to read the "Flag" book, we need to be admin. 

Hints are all about tampering with JWT token and digging source file to create a new JWT token. 

From the source code it is clear that website is using JWT token to authorize the user and give access to books according to their roles.


<img width="371" alt="image" src="https://user-images.githubusercontent.com/66155978/226203837-bc11b9e3-0ba8-44d4-9642-2a253a41330e.png">

The JWT field contains-  Role, Email, and UserID as main keys and HMAC algorithm. which we need to modify. So lets fire up Burpsuite and capture the book reading request.

<img width="408" alt="image" src="https://user-images.githubusercontent.com/66155978/226204142-86ecd601-2e69-4c81-8b8b-be97e55bf013.png">


So here's the JWT token being used so let's modify it. 

<img width="480" alt="image" src="https://user-images.githubusercontent.com/66155978/226199293-c2e43cb1-c7ad-4625-80f3-a92d4e7da2bf.png">


<img width="788" alt="image" src="https://user-images.githubusercontent.com/66155978/226199140-37c59f8b-c467-4321-9599-ff0145c962af.png">

There are only two users initialized and userid 1 is of "user" so am assuming userID of Admin must be 2. Giving 1234 in Payload. Next is to copy the payload and replace with the original one, Also we need to change the book number, free one is 3 so, admin one might be 5.

<img width="459" alt="image" src="https://user-images.githubusercontent.com/66155978/226199558-b1ad802f-efa8-4403-ac9f-d70f53d5415a.png">

All set ..let's hit the forward button...... and yayyy we got the flag..

<img width="960" alt="image" src="https://user-images.githubusercontent.com/66155978/226199110-18c5abb6-0747-4632-9910-47a659cd4147.png">


## Flag 

picoCTF{w34k_jwt_n0t_g00d_ca4d9701}
