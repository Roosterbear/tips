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



