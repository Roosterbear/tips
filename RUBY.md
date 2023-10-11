# RUBY

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

## Variables

* You don't need to declare a variable or specify a type. <br/>
* Just assign a value to the variable and that's all!. <br/>

## Methods

* You don't need to use parenthesis if they don't have parameters. <br/>
* You can use _?_ at the end to say it will return a boolean, as question. _empty?_<br/>
* You can use _!_ at the end if it will change the parameter. _change!_ <br/>

## Conditions

```ruby
if !name.empty?
  puts name
end
```

## Iteration

```ruby
list.each do |number|
  puts number
end
```

## Classes

```ruby
class Person
  def initialize
    puts "This is a person!"
  end
end

a_person = Person.new
```

## Accessors

* If you need to access to an instance variable (_@name_) you will need getters and setters. <br/>
* You have getters and setter in a better way: __accessors__. <br/>

### attr_accessor

We now have a _getter_ and a _setter_ <br/>

```ruby
class Person
  attr_accessor :name
  def initialize(name)
    @name = name
    puts "This is a person!"
  end
end

a_person = Person.new
puts a_person.name
a_person.name = "Nobody"
puts a_person.name
```

### attr_reader

We just have a _getter_ <br/>

```ruby
class Person
  attr_reader :name
  def initialize(name)
    @name = name
    puts "This is a person!"
  end
end

a_person = Person.new
puts a_person.name
```

## Symbols

* They are made of characters, but have a colon (_:_) before them. <br/>
* They are _UNIQUE_ <br/>
* In Hashes, they are used as _KEYS_

## CLEAN CODE

### Readability

```ruby
def sum(a,b)
  a+b
end
```
### Extensibility

```ruby
def log(message, level)
  puts "#{level.to_s.upcase}: #{message}"
end
```

### Simplicity

```ruby
log("An error occurred", :error)
```


