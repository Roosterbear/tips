# Ruby and Rails

## Installation

>ruby -v
>sudo apt-get update
>sudo apt-get install ruby-full
>ruby -v
>gem install rails
>rails -v
>gem install bundler

_if it is not ruby current version:_ <br/>
>rvm use ruby-3.2.0
_if rvm is not installed:_ <br/>
>\curl -sSL https://get.rvm.io | bash -s stable
>rvm list known

---
---

# RUBY



---
---


# RAILS

## Start Project 'cabinet'

>rails new cabinet

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

