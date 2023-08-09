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



## Start Project

_create welcome controller and index view_ <br/>

>rails generate controller welcome index

_create routes_ <br/>

* rake routes is deprecated starting from rails 6.1!, instead: <br/>

>rails routes

_make a controller our starter page:_ <br/>

__app/config/locales/routes.rb__ <br/>

>root 'welcome#index'


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

