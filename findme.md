# findme

## Challenge Info 

Tags: Web exploitation

AUTHOR: GEOFFREY NJOGU

## Description
Help us test the form by submiting the username as test and password as test!

## Solution 

There is a simple website asking to login with the given creds. On succesful login it redirects us to another page.
The redirected page has a search bar but nothing useful is there as it doesn't yields any output. 

Notice, there is some encoding in the URL before the page is redirected to the final website, maybe that's our flag. 

<img width="778" alt="image" src="https://user-images.githubusercontent.com/66155978/225605197-56dfc55e-5ad4-4d9b-b294-fe61048664b9.png">

1. Let's intercept the login request and try to capture that fast moving URL. 
2. So from the first redirection we get our 1st part of the flag after decoding it using base64

<img width="458" alt="image" src="https://user-images.githubusercontent.com/66155978/225606390-79fd5985-d6c9-4d83-99e5-56b88c2a1194.png">

3. Forward the request and capture the 2nd redirection. 

<img width="289" alt="image" src="https://user-images.githubusercontent.com/66155978/225606813-1d5bb59c-0a9a-4a9b-af69-bff7f9f98ccb.png">

4. Combine both the encoding and decode it from base64 to get the flag. 

<img width="512" alt="image" src="https://user-images.githubusercontent.com/66155978/225606918-852dc504-2f7f-4e6c-994b-1cc98f758177.png">


## Flag

picoCTF{proxies_all_the_way_be716d8e}
