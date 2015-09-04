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


