Christopher Shorkey
CSCI 641

I created two virtual machines using VMware workstation pro hypervisor. I have a Windows11 attacker and an Ubuntu victim with OWASP Juice shop. The juice shop is intentionally vulnerable to web attacks. 

![[Windows Attacker Screen Shot.png]]

![[Ubuntu Victim Screen Shot.png]]

The first exploit in the OWASP Juice Shop path is web based. There are some basic things to do in Juice Shop, including finding the admin's email and figuring out the search criteria in the browser's search bar. A real exploit to do however, is a SQL injection. By understanding how the database behind Juice Shop stores data, it is possible to get that database to return things it was not meant to. The tutorial I followed used burp suite to intercept traffic and analyze it. After analyzing the request we made when trying to login the first time, we can see that by starting a query with  ‘ or 1=1 —, it returns everything that is a string or true. This exploit allows the attacker to take the admin's credentials and use them to login. This is the exploit and the steps that were used to follow it.