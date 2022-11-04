# Pen Testing Live Targets

Time spent: **2** hours spent in total

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

Vulnerability #1: SQL Injection

Description:
The injected SQL command was %27%20OR%20SLEEP(5)=0--%27, I replaced the Salesperson's ID number from the URL with the SQL command. Which takes a few seconds while quering the data.
<img src="![Blue](https://user-images.githubusercontent.com/112200901/200057325-d60b43a8-0187-496c-a178-3058cd9b6159.gif)">
![Blue](https://user-images.githubusercontent.com/112200901/200057577-2d1ec754-e4c8-4a23-9625-f355982ffe1a.gif)


## Green

Vulnerability #1:Cross-Site Scripting XSS

Description: The Green website has a mistake in their code that allows the site vulnerable to a stored XSS attack. The first step was to create a feeback post, and insert <script>alert('XSS found the XSS!');</script> in the message portion. Then you have to sign on to an admin profile to view the feedback messages. Once you try to view the feeback messages, a pop up should come up that says I found the XSS!

<img src="![Green](https://user-images.githubusercontent.com/112200901/200052417-34cba62a-5aa5-4c2e-994b-5d4adf34740c.gif)">

![Green](https://user-images.githubusercontent.com/112200901/200058009-cb7c3c03-299f-49a9-b1f9-ca2c551a1a8a.gif)


## Red

Vulnerability #1: Insecure Direct Object Reference

Description: The red website is missing a specific code which allows an attacker to view sensitive information. If i change the ID field in the URL to numbers 10, 11, 12, and 13 I can see other sensitive information that hsould not be public. 

<img src="red-vuln1.gif">

![red](https://user-images.githubusercontent.com/112200901/200060651-58e1d49d-8845-4793-95cb-4761e2c1d0eb.gif)

## Notes

Describe any challenges encountered while doing the work

One of the main challenges was finsing out which websites had those vulnerabilites, so there was a lot of trial and error that took some time. Other than that, this was a fun practice assignment. 
