# RubyonRails-CommandLine-Syntax
This repository is a list of Command Line features used in the process of creating Rails applications. It also contains Ruby syntax for the usage of Rails development, but also includes resources of information for learning and using Ruby on Rails. In other words its more of a Rails cheat Sheet. Feel free to add more information that will be helpful for new and advance users of Ruby on Rails.

###Ruby on Rails Part 1:


#####Creating a Rails application
```
rails new 'appname'
```
#####To install all the necessary gems for your Rails application
```
 cd appname/
 
 bundle install
```

#####Connecting to the Rails to the server
```
rails server
```
#####updating the gems in the rails application
```
bundle update
```
#####Updating database
```
bundle exec rake db:migrate
```
#####To See all Rake task available
```
bundle exec rake -T
```

#####An important feature for changing the format from RDoc to Markdown
```
git mv README.rdoc README.md
```
#####Controller generation
```
rails generate controller ControllerName <optional action names>

Example: rails generate controller staticPages home about contact help
```

###Rails shortcuts
| Full command        | Shortcut  | 
| ------------- |:-------------:| 
| rails server     | rails s | 
| rails console      | rails c |   
| rails generate | rails g |    
| bundle install | bundle |    
| rake test | rake  |    

#####Rails Console
 ````
 rails console
 ```

#####Rails Destroy
```
rails destroy
```
######Destroys the controller
```
rails destroy controller ControllerName <optional action names>
```
######Destroys the model
```
rails destroy model ModelName
```
#####Undoing a sinlge migration
```
bundle exec rake db:rollback
```
#####To go all the way back to the beginning and undoing the first migration
```
bundle exec rake db:migrate VERSION=0
```
###Manually adding action/controllers to your  Rails application
In your file directory you first go to your routes file

**config/routes.rb**

The example we will be using is contact. Add contact to the routes file

```ruby
Rails.application.routes.draw do
  get 'ControllerName/actionname1'
  get 'ControllerName/actionname2'
  get 'ControllerName/contact'
  
end
```
From there we add contact to the controller go into your file directory for the controller.rb file

**app/controllers/controller_name.rb**

Add the following:

```ruby
class ControllerName < ApplicationController

  def actionname1
  end

  def actionname2
  end

  def contact
  end
end
```
Finally you create the action contact file : contact.html.erb. You can add this manually or using the command line

#####Touch is used to add files 
```
touch app/views/ControllerName/contact.html.erb

```
After adding the contact.html.erb file then you are finished. You have manually created a action/controller into your Rails application.

#####Change files name temporarily
 ```
 mv app/views/layouts/application.html.erb layout_file 
```
#####To retore/rename the file
 ```
 mv layout_file app/views/layouts/application.html.erb 
```
#####Setting up a root route

To set up a root route go into your routes.rb file

**config/routes.rb**
 ```
root 'ControllerName#actionname1'
```
 ```ruby
  Rails.application.routes.draw do
   root 'ControllerName#actionname1'
   get 'ControllerName/actionname2'
   get 'ControllerName/contact'
   
 end
```
###Ruby on Rails Topics

[Embedded Ruby](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Embedding-Ruby-erb.md)


[Git Basic Commands](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Git-Basic-Commands.md)

[Heroku Setup](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Heroku-setup.md)

[Issues](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Issues.md)

[Ruby Programming Language](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Ruby-Programming-Language.md)



[Testing](https://github.com/JonathanMoreno14/RubyonRails-CommandLine-Syntax/blob/master/RubyonRails-Topics/Testing.md)


