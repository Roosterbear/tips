# Heroku Guide for RoR

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
