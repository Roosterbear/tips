# Ruby on Rails

* Think about Rails as a huge Ruby Library. <br/>
* Rails provides a _framework,_ that is, a software library that provides utilities, conventions, and organizing principles to allow us to build complex web applications.
* Usually, web applications accept user requests, query databases and responds with data rendered in templates. <br/>

### Don't repeat yourself
### Convention over configuration

## Installation

* Check Ruby installation <br/>
* Install _RVM_ Ruby Version Manager <br/>

### See Ruby versions

>rvm list

### Create a gemset

>rvm use ruby-2.4.1@lear-rails --create
>gem install rails


### Start a Project

>rails new project
>cd project

__run server__ <br/>

>rails server

* We currently use __Puma__ as Web server, and not _WEBrick_ 



_create welcome controller and index view_ <br/>

>rails generate controller welcome index


_create routes_ <br/>

* rake routes is deprecated starting from rails 6.1!, instead: <br/>

>rails routes


_changing our starter page:_ <br/>

__app/config/locales/routes.rb__ <br/>

>root 'welcome#index'

_adding gems_ <br/>

* Go to: __https://rubygems.org/__ 
* Look for a gem
* Copy the gemfile line 
* Past it in gemfile
* Exec __bundle install__
<br/>


__haml__ <br/>

* Add haml gem
* Change _.erb_ from your view to __.haml__
* Add __%h1 Hello haml__ to test


__generate a model__ <br/>

>rails generate model Doc title:string content:text

>rake db:migrate


__generate the controller ( IN PLURAL ) for the model__ <br/>

>rails g controller Docs

Add actions: <br/> 

* index
* show
* new
* create
* edit
* update
* destroy

__INSIDE__ our new controller <br/>









--

--



## Heroku Guide for RoR

##### curl https://cli-assets.heroku.com/install.sh | sh #####

#### heroku keys:add ####

### heroku create ###
### git remote ###

## rails new proyecto ##
## rails generate scaffold car make:string model:string year:integer ##
## rails db:migrate ##

In Gemfile replace instead gem 'sqlite3'

group :development, :test do
 gem 'sqlite3'
end

group :production do
  gem 'pg'
end

#### bundle config set --local without production ####
#### bundle install ####

Config > routes.rb

Rails.application.routes.draw do
  root 'cars#index'
  resources :cars
end

## Let's GIT ##
git add .
git commit -m 'updates for heroku deployment'
git push origin main
git push heroku main

heroku run rails db:migrate
heroku open

