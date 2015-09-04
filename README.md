# RubyonRails-CommandLine-Syntax
This repository is a list of Command Line features used in the process of creating Rails applications. The repository also includes Ruby syntax for the usage of Rails development. In other words its more of a Rails cheat Sheet.


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
rails sever
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
###Manually adding action/controllers to the rails app
In your file directory you first go to your routes file

**config/routes.rb**

For example we will add contact to the routes file

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
class StaticPagesController < ApplicationController

  def actionname1
  end

  def actionname2
  end

  def contact
  end
end
```

