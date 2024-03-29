# Pen Testing Live Targets

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection (SQLi)

Description: 
* Eve, the attacker, can first see that a potential IDOR vulnerability is shown by switching the id in the URL to some consecutive number. 
* We can change this ID into some consecutive number and access another salesman page.
* After this, we found out that SQLi is a vulnerability within this page/website.
* Enter the following command for an SQLi: %27%20OR%20SLEEP(5)=0--%27
* After entering the SQLi command, you will see that it does not say "database query failed", but it rather shows that the SQLi was queried.
* The result of this shows that the web page sleeps for 5 seconds due to the query. The following is shown in the gif below:

![blue_pentest#1](https://user-images.githubusercontent.com/96878742/200104845-2bab7c50-953d-4e40-8375-3e35ea1641e2.gif)


## Green

Vulnerability #1: Cross-Site Scripting (XSS)

Description:
* Eve, the attacker, can first see that there could be a potential XSS attack through the feedback form in nay of the entries.
* Eve, aka Meer A., then injects the following XSS script into the feedback form: 
    * <script>alert('Meer A. found the XSS!');</script> 
* Then, once you go onto the feedback page, the XSS script that was injected in the feedback form gets ran.
* The following is shown in the gif below:
* NOTE: My specific script wasnt shown in the .gif file due to the very long mp4 (would've had to screen record through a lot of gifs) it would've had, so I wouldn't be able post it on github without it saying it is a large file. This is confirmed to work as I manually went through all the XSS scripts injected into the website and saw my own injected XSS script to work. Nevertheless, the .gif to demonstrate this XSS vulnerability is below:

![green_pentest#1](https://user-images.githubusercontent.com/96878742/200104851-667bcf2f-15f1-4ad1-95b5-ea1c68a1eb70.gif)


## Red

Vulnerability #1: Insecure Direct Object Reference

Description:
* Eve, the attacker, can first see that there could be a potential IDOR (Insecure Direct Object Reference) attack by traversing through the ID of the webpage at the top which represents some salesperson.
* We see from the salesperson page that we can access up to 9 different salesperson, and this is respresented with their ID 1-9 in the URL of the webpage.
* We change ID to 2, then 4 and they work as expected.
* Then, we change the ID to 10 which is beyond tha range, then we access a page that we were not supposed to. id = 11 works as well with the name of the salesman being "Lazy Lazyman".
* THus, we have traversed the website and displayed an IDOR (Insecure Direct Object Reference) attack by doing so.
* The gif displaying this is below:

![red_pentest#1](https://user-images.githubusercontent.com/96878742/200104861-f33b4054-0178-4a2a-85a2-4c6d89bd6d4c.gif)


## Notes

Describe any challenges encountered while doing the work.

Some challenges that I faced while doing this challenge was just realizing when to use what type of vulnerability attack. In order to find a vulnerability, you must come to a webpage or look at something with a clear mind and possibly brute force or think of any way possible to break the security of the system or webpage. To approach these problems, you must have an immense amount of creativity backed with the knowledge on all the different vulnerabilities, which is why assignments like this are difficult. Although they are difficult, they are not impossible. Everything is ambiguous at first since there isn't a given hint to tell you where to go when hacking a website, displaying the real life applciation of this assignment. Overall, a challenge I encountered with this assignment was trying to be as creative as possible and think of some way to break the security of this webpage.
