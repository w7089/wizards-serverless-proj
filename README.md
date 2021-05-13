# Location-specific online store

## Table of Contents

- [Idea](#Idea)
- [Demo](#Demo)
- [Usage](#Usage)

## Idea <a name = "Idea"></a>
 
 EdgeWorkers + EdgeKV can be used in location specific online store. The store will show products according to the user's geolocation. Javascript code similar to presented [here](https://developer.akamai.com/blog/2020/06/11/edgeworkers-use-case-fast-geolocation) will run on EdgeWorker and set user geolocation  in a cookie. The cookie value will cause website language and displayed products to correspond to a user's location. This in turn will cause the appropriate location-specific store products stored in EdgeKV to be retrieved with low latency from the closest to the user EdgeKV instance.

## Demo <a name = "Demo"></a>

Demo project demonstrates an international online store which has 2 products (Israeli and US) and 2 users (one from Israel and one from US). 

Once a user logs in and navigates to `Shop` location specific products only are displayed to the user. Sample website is based on Wordpress stack + several Wordpress plugins which allow to showcase the functionality of location specific online store. 

## Usage <a name = "Usage"></a>

- Clone the repo

`git clone git@github.com:w7089/wizards-serverless-proj.git`

- Launch sample website

1. `cd wizards-serverless-proj`
2. `docker-compose -p=wizards -f stack.yml up -d`

- Import website data using phpmyadmin.

1. navigate to `http://localhost:8020` (user=exampleuser,password=examplepass)
2. go to Import tab, import db.sql file


- Access the website in the browser `http://localhost:8010/my-account/`
- login as `us` user `12` password, navigate to `http://localhost:8010/shop`. You should see US product if you located in US
- login as `il` user `12` password, navigate to `http://localhost:8010/shop`. You should see Israeli product if you located in Israel
