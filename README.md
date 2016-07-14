# IntrovertSecurity
IntrovertSecurity - opening the door only for friends that call in advance

This project is intended to help non-technical persons that have an online "hobby" (blog, presentation site, etc.) by adding an extra layer of security to their Virtual Private Server that run Linux.
On a typical Wordpress VPS there are a couple of services running: apache, ftp server, ssh , mysql, phpmyadmin, webmin, maybe a mail server. 
Not all these services need to be reachable from the exterior(internet). Nowadays there are increasingly more automated attacks targeting VPSs with the purpose of compromising the server so it can be incorporated in a botnet network.

The best protection is prevention! 

So why keep port 10000 open if you rarely access webmin? Why is ssh  round the clock accessable from the internet? 

I propose a black hole aproach : not respond to anything on specific ports  if you don't know it's from a friend. 

![alt tag](https://raw.githubusercontent.com/WeLikeCode/IntrovertSecurity/master/docs/img/general_arhi.jpg)

A client application runs on the vps and blocks webmin port , for example. When you need to login into the webmin panel, you first access the "Master panel" (Server from the picture), which creates a ticket for you. The ticket contains data about your IP, time to live and ports to be opened.  
The client running on the VPS checks every 10 seconds the "Master panel" for tickets. When it gets one, it opens the ports for your IP. 

The "Master panel" is designed to be a very light google cloud deployable web application that will you google authentication. 

Code coming soon ! :) 
