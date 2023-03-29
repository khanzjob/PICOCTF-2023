# who is it

## challenge Info 

Tags: Forensics, email

AUTHOR: JUNIAS BONOU

Points: 100

## Description
Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam.
Can you help us identify whose mail server the email actually originated from?
Download the email file here. 

Flag Format: picoCTF{FirstnameLastname}


## Solution 

Nothing interesting is there in email, also the attachment is pretty much useless. 

<img width="364" alt="image" src="https://user-images.githubusercontent.com/66155978/225938468-ad33d1e3-f3df-40e4-bc37-3cf15828916e.png">

1. Open the file using sublime text to see the email headers in detail.( ALos, it can be configured to automatically highlight and spot the email header's details easily)
2. One IP address is given in the headers.

<img width="740" alt="image" src="https://user-images.githubusercontent.com/66155978/225944072-f315e1a2-cc12-4c2d-b23f-ef57e3042ab8.png">


3. Search IP address using whois tools and there we can find the name of the person to whom the server belongs. 

<img width="328" alt="image" src="https://user-images.githubusercontent.com/66155978/225944365-55656a69-33b7-4470-ac5f-03c1c51aea5c.png">


## Flag

picoCTF{WilhelmZwalina}
