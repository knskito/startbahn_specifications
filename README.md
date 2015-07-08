[![Build Status](http://ci.startbahn.org:8080/buildStatus/icon?job=startbahn-pull-request)](http://ci.startbahn.org:8080/job/startbahn-pull-request/)
# startbahn_specifications
Startbahn is an social networking service (SNS) for art communities.


## Source Code

There are a few different ways you can download startbahn app:
* Download the zip file from the [release] (https://github.com/startbahn/startbahn/releases/)
* Checkout the source: `git clone https://github.com/startbahn/startbahn.git`

## Pre Installation
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

## Installation
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


## Startup
* foreman  will start redis-server, sidekiq and web server. Run the foreman by:
  `foreman start`
* open app in web browser: http://localhost:3000
* login using:
  username: admin@startbahn.jp
  password: password

## Accounts
there are four kinds of accounts in Startbahn
* General
* Artist
* Reviewer
* Collector

All users can

1. follow accounts
2. edit their own profile
3. thumb up or down reviews
4. search Startbahn
5. mark works,reviews,threads and events
6. read works,reviews,threads and events
7. quit Startbahn


General accounts can
* change General Accounts to artist,reviewer or collector account
Artist accounts can
* register works
Reviewer accounts can
* review works
Collector accounts can
*



## Follow and Mark

##Auctions
There are two kinds of auctions
* Primary Auction
* Secondary Auction
