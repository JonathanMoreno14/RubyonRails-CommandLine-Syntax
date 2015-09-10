#Ruby on Rails Part 2

##Setting up  root routes 

#####Rails Routing
The root path is routed to the controller and action that we choose to incorporate. As you can see the root path is designated for the actionname1, this can be for exmaple the home page of your web application or anything of your choosing. 

**Before:**

**config/routes.rb**

```ruby
  Rails.application.routes.draw do
   root 'ControllerName#actionname1'
   get 'ControllerName/actionname2'
   get 'ControllerName/contact'
   
 end
```

**After:**

Routing for the ControllerName

**config/routes.rb**

```ruby
  Rails.application.routes.draw do
   root 'ControllerName#actionname1'
   get  'action2' =>  'ControllerName#actionname2'
   get  'contact' => 'ControllerName#contact'
   
 end
```

This creates name routes that we can use to by name or raw URL.
```ruby
root_path -> '/'
root_url  -> 'http://www.example.com/'

```
We use the **link_to** function with the named routes (**root_path**)

You can name routes anyway you want.

```ruby
#From this:
<%= link_to "Contact", '#' %>

#To this:
<%= link_to "Contact", contact_path %>

```

Adding the main **root_path** 

*In this example I'm using their Actionname to show which named route belongs to which*

Lets say you have a navigation bar and you want to have the logo be an actual link then you would add **root_path** 

```html
<header class="navbar navbar-fixed-top navbar-inverse">
  <div class="container">
    <%= link_to "Rails Web Application", root_path, id: "logo" %>
    <nav>
      <ul class="nav navbar-nav navbar-right">
        <li><%= link_to "Actionname1",    root_path %></li>
        <li><%= link_to "Actionname2",    action2_path %></li>
        <li><%= link_to "Contact", contact_path %></li>
      </ul>
    </nav>
  </div>
</header>


```




