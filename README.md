**startbahn**
====
startbahn is a service optimized for art communities which includes both social networking service (SNS) and online auction.

##Outline
1. [Specifications](#specifications)
2. [Install](#install)
3. [Contribution](#contribution)
4. [License](#license)

#<a name="specifications">1. Specifications

## 1.1 Accounts
startbahn is composed of the following four accounts.
* **General**
* **Artist**
* **Reviewer**
* **Collector**  
<!--Pictogram would be here for intuitive understanding.-->  

We can choose only one account and cannot change the role after the decision, except General account.  
(General is an account for understanding overall system of startbahn. Although its function is strictly regulated, General can change its role to one of the other three accounts for once.)

###All accounts can
* follow other accounts.
* edit their own profile.
* thumb up or down reviews.
* mark works, reviews, threads and events.
* post comments on review.
* make or read threads in Forum.
* post events.
* send invitations of startbahn.

###General accounts can
* change its role to Artist, Reviewer or Collector.

###Artist accounts can
* post, edit and remove their artworks on startbahn.
* put their artworks up for Primary Auction.
* obtain re-distribution value through Secondary Auction. (re-distribution system will be described [later](#rd_system) in detail.)

###Reviewer accounts can
* review artworks posted by Artist.
* edit and remove their reviews.
* obtain re-distribution value through Primary and Secondary Auction. (re-distribution system will be described [later](#rd_system) in detail.)

###Collector accounts can
* buy posted artworks as collection by bidding at Primary and Secondary Auction.
* resale their collections on Secondary Auction.

Functions on each accounts are explicitly differentiated according to the real art market.  
We believe artistic value can be incremented online by their interaction.  
<!--Pictogram would be here for intuitive understanding.-->

##1.2. Auctions
Posted artworks can be circulated through the following two auctions in startbahn.
* **Primary Auction**
* **Secondary Auction**
<!--Pictogram would be here for intuitive understanding.-->  

###Primary Auction
* The auction for **Artist as the seller** and **Collector as the bidder**.
* All bids are sealed that only an Artist as the seller can check the bidder and the price of each bids.
    * Other accounts can only check the number of bids.
* **Artist as the seller can select the buyer regardless of bidding prices after the end of auction.**

###Secondary Auction
* The auction for **Collectors as both the seller and the bidder**.
* All bids are opened that every accounts can check the bidder, price and the number of bids.
* **The Collector who bidded the highest price is automatically selected as the buyer at the end of auction.**

Primary Auction is a kind of substitution for gallery system in the real art market; it can prevent from excessive deals just for the short-term profit and can contribute to the development of artistic value in circulated artworks combined with the following re-distribution system.
<!--Pictogram would be here for intuitive understanding.-->  

##<a name="rd_system">1.3. Re-Distribution System
### 
### Rates

##1.4. Other Characteristics
### Follow and Mark

##1.5. Terms
### Terms of Use
### Privacy Policy
### FAQ

##Appendix



#<a name="install">2. Install

## 2.1 Source Code
There are a few different ways you can download startbahn app:
* Download the zip file from the [release] (https://github.com/startbahn/startbahn/releases/)
* Checkout the source: `git clone https://github.com/startbahn/startbahn.git`

## 2.2 Pre Installation
* Install rbenv & ruby-build
  for MacOS X
  `brew install rbenv ruby-build`
* Install ruby with rbenv
  `rbenv install 2.2.2`
* Install npm
  for MacOS X
  `brew install node`
* Install bower
  `npm install bower -g`
* Install qt for capybara-webkit
  for MacOS X
  `brew install qt`
* Install redis
  for MacOS X
  `brew install redis`

## 2.3 Installation
* Extract the installer
* Go to startbahn folder
* install required gems:
  `bundle install`
* start mysql server
  `mysql.server start`
* install foreman:
   `gem install foreman`
* configure the installation, use the .yml.configuration inside config folder as a template:
  `./script/init_config_ymls.sh`
  or copy file manually
  `cp database.yml.example database.yml`
  `cp paypal.yml.example paypal.yml`
  `cp startbahn.yml.example startbahn.yml`

  Please ask the admin for aws secret key
* install bower dependency:
  `bundle exec rake bower:install`
* create, install the database and add administrator account:
  `bundle exec rake db:create db:migration db:seed`


## 2.4 Startup
* foreman  will start redis-server, sidekiq and web server. Run the foreman by:
  `foreman start`
* open app in web browser: http://localhost:3000
* login using:
  username: admin@startbahn.jp
  password: password

#<a name="contribution">3. Contribution

#<a name="license">4. License
The MIT License (MIT)

Copyright (c) 2015 startbahn,Inc

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
