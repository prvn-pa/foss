---
layout: post
title: "Linking A Custom Domain To Github Pages"
date: 2022-08-28 12:50:00 +0300
background: '/img/ps-05.jpg'
---

## STEP 1

Make sure you have domain. I use Google Domains.

## STEP 2

Go to Github `username.github.io` repository. Then to settings and left side there should be an option called `Pages`. In which enter your domain name and save. 

**Note:** You may need to put a `CNAME` file in your repo just with the domain name.

## STEP 3

Now go to DNS management (in my case its Google domains) in your domain provider site and set the following Records.

Host = www; Type = CNAME; TTL = 600 (10 Mins); Data = username.github.io

Then create four more additional records in the same console.

Name = @ (Or Keep Empt); Type = A;   
Value= 185.199.108.153; 185.199.109.153; 185.199.110.153; 185.199.111.153 (Create under same name); TTL = 600

Save that and wait some time till the DNS propagation.
