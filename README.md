# An implementation of EAP/802.1x Wireless Network with FreeRADIUS

This is a FreeRADIUS configuration used to implement an EAP/802.1x wireless network. The following features are implemented. 

##Features:
* Wireless access using EAP authentication. Wireless users log onto the wireless network using username and password. Each user will have a its own profile. This profile contains: mobile number, email, first name, last name etc.   
* Each user's network traffic will be limited to monthly quota. This quota includes both uploads and downloads. Once the quota is reached, user will be disconnected from the network. 
* Network quota reset every month on a given date. For example, quota resets on 3rd of every month. 
* Users can be managed via user groups. This means that the same network policy can be applied to a group of users. A network policy could be like, 50 G of quota and reset on 3rd of every month.
* Restrict users to certain network access points. For example, the user group students can only have access to the NAS located in the science block. 
* Send user data usage warning messages via email and SMS. Once the user reached 50%, 80% or 100% of its quota, a warning message will be sent through both email and SMS.

This is the environment used to implement the wireless network with EAP authentication.  
##Environment: 
* Email server:  mailgun.
* SMS gateway: [smsgateway.me](smsgateway.me). 
* NAS (dynamic ip): Mikrotik.
* Radius server (static ip): FreeRADIUS Version 3 hosted with CoreOS + Docker.
* GUI for user management: [OWUMS](https://github.com/openwisp/OpenWISP-User-Management-System/wiki) hosted with CoreOS + Docker.

##Prerequist:
*Cron.
*Curl
*Perl

##Configuration:
To use this implementation two sets configuration data needs to be correctly completed. 

###Radius Data:
All the radius data is store in the mysql database. 

###Email and SMS:
config_data.pm

###Cron job:

##Docker 

##Build Docker image

##Run Docker image


This guide is to show you how to configure free radius to implement the above features base upon the above environment. Any things beyond the aforementioned features and environment will be exceeding the scope of this guide. All the necessary configurations files are published here. You only need to change some basic settings to get it working in your environment. This guide is to show you how what these settings are and how to change it.

As a way of self documentation, this guide will also explain how the mentioned features are implemented. To understand how this

##Assumption


Freeradius does not include any graphical interface. It will be nice for users to see their network usage or change their password. Also user administrators need an initiative interface to manage its users. This need is meet by OWUMS. This free radius configuration is designed to work with OWUMS. For the OWUMS setup pleas refer this github. 

All the configuration is manually edited. If you want to modify any the features listed above you will need find your own solution. For example, if you want to have the internet quota to count only download traffic, you will need to change the code yourself. 

