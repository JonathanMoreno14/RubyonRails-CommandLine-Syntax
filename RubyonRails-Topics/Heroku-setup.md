##First time set up for Heroku for Windows machine
When delpoying your Rails app into Heroku for the first time make sure to download the Heroku tool belt for your machine, in this case Windows. 
###Steps:
Create account on Heroku or if already have an account sign in
Then open your Rails project Gemfile and remove
```ruby
     # Use sqlite3 as the database for Active Record
     gem 'sqlite3'
```
     
Add it at the bottom of the Gemfile you will be adding a new group designated for production with the following
```ruby
     group :development do
         gem 'sqlite3'
      end
      group :production do
         gem 'pg'
         gem 'rails_12factor'
      end
```
    
After the gems have been added we will run bundle install
```
     bundle install --without production
```
Once the bundle is installed in your git bash terminal run
```
     heroku login
```
Upload your credentials
From there you will need to initilaize a git repo within your Rails project. If you have already have a git repository in your Rails project folder all you will need to do is add the updated files and commit to the master repository. I ran into an issue when I first deployed it to Heroku. 

Next in your git bash type:
```
    heroku create
```

Once Heroku is created you will see a custom URL followed by herokuapp.com
You will need to push the git folder into heroku to finalize the deployment
    git push heroku master
The last thing you will need to do is in your git bash terminal you will need to migrate your database
    heroku run rake db:migrate
Finally to open your heroku app and view it on your web browser
    heroku open
======Side note 1: If you accidently delete your Rails application on heroku
If you delete it by accident and your trying to utilize git push heroku master and there is an error such as this one:
       ! No such app as heroku-app-name-here.
       fatal: Could not read from remote repository
Then follwoing will remove the first herouk master file 
     git remote rm heroku
This will let you add a new heroku master file and be able to push the application to heroku.   

======Side note 2: If you are having problems with heroku you can use heroku logs to check the problem
      heroku logs

