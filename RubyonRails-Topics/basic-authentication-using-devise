##Creating a basic authentication system using Devise

If you are using git bash or Terminal..etc..

The first step is to get the Ruby Gem, **Devise** and copy the **gem** file. 

[Ruby Gems](https://rubygems.org/gems/devise/versions/3.5.6)
and add it to your gemfile **app/Gemfile**

```
gem 'devise', '~> 3.5', '>= 3.5.6'
```

Proceed with a bundle install

```
bundle install
```

After the bundle has been installed you will need to install Desive 

```
$ rails g devise:install
       DL is deprecated, please use Fiddle
      create  config/initializers/devise.rb
      create  config/locales/devise.en.yml
```

**Once Devise is installed** 

You will see a prompt on your Git Bash/Terminal:

===============================================================================

Some setup you must do manually if you haven't yet:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:

       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

  4. If you are deploying on Heroku with Rails 3.2 only, you may want to set:

       config.assets.initialize_on_precompile = false

     On config/application.rb forcing your application to not access the DB
     or load models when precompiling your assets.

  5. You can copy Devise views (for customization) to your app by running:

       rails g devise:views

===============================================================================

#####You will need to set up a User model

```
$ rails g devise User
      DL is deprecated, please use Fiddle
      invoke  active_record
      create       db/migrate/20160413163637_devise_create_users.rb
      create    app/models/user.rb
      invoke    test_unit
      create      test/models/user_test.rb
      create      test/fixtures/users.yml
      insert    app/models/user.rb
       route  devise_for :users
```

#####Once the User model have been set up, you will update the db

```
$ rake db:migrate 
```

#####The last step is to generate views 
```
$rails g devise:views 
```


###Basic Setup for using Desive on Ruby on Rails.

You will need to add the sign up and login attributes to the layout for the application.html.erb

**app/views/layouts/application.html.erb**

```
  <% if(!user_signed_in?) %>
              <li><%=  link_to "Sign Up", new_user_registration_path %></li>
              <li><%=  link_to "Login", new_user_session_path %></li>
  <% else  %>
            <!-- Dropdown Trigger -->
              <li><a class="dropdown-button" href="#!" data-activates="dropdown1"><%= current_user.email %><i class="material-icons right">arrow_drop_down</i></a></li>
  <% end %>
```

Then you add the flash messages on **app/views/layouts/application.html.erb**

```
<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>
```

*It's better to add the flash messages under the header*

Finally, for logging out of the web application you would add

```
<%= link_to "Log out", destroy_user_session_path, method: :delete %>
```
into the specified location for the logout, a great example is when you have a dropdown menu for the user, once he or she has signed in. The log out will show. 

```
<ul id="dropdown2" class="dropdown-content">
    <li><a href="#!">My Profile</a></li>
    <li><a href="#!">My Courses</a></li>
    <li class="divider"></li>
    <li><%= link_to "Log out", destroy_user_session_path, method: :delete %></li>
  </ul>
```


To check and view the forms you would need to run the Rails server

```
$rails s
```

In the address bar you will type 

**localhost:3000/users/sign_up** 

or 

**localhost:3000/users/sign_in**

It will take you to the sign-up and/or the sign in form. 

You can test the code by running rails server and using a test email and password. You can view Devise functionalities on the web application. 
