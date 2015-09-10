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


###Partials

Partials *"are another device for breaking the rendering process into more manageable chunks. With a partial, you can move the code for rendering a particular piece of a response to its own file."* [Rails API -Layouts and Rendering](http://guides.rubyonrails.org/layouts_and_rendering.html#using-partials)

Example:
This HTML doc seems cluctered, its readable but you would prefer to reduce the lines of code. You do this by Partial. 

```html
<!DOCTYPE html>
<html>
  <head>
    <title><%= full_title(yield(:title)) %></title>
    <%= stylesheet_link_tag 'application', media: 'all',
                                           'data-turbolinks-track' => true %>
    <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
    <%= csrf_meta_tags %>
    <!--[if lt IE 9]>
      <script src="//cdnjs.cloudflare.com/ajax/libs/html5shiv/r29/html5.min.js">
      </script>
    <![endif]-->
  </head>
  <body>
    <header class="navbar navbar-fixed-top navbar-inverse">
      <div class="container">
        <%= link_to "Rails Web Application", '#', id: "logo" %>
        <nav>
          <ul class="nav navbar-nav navbar-right">
            <li><%= link_to "Actionname1",   root_path %></li>
            <li><%= link_to "Actionname2",   action1_path %></li>
            <li><%= link_to "Contact", contact_path %></li>
          </ul>
        </nav>
      </div>
    </header>
    <div class="container">
      <%= yield %>
    </div>
  </body>
</html>

```

#####Using Partial


To begin using partial we will be using **render** which *"Renders the content that will be returned to the browser as the response body"* [Render - Rails API Dock](http://apidock.com/rails/ActionController/Base/render)

We start by creating two files for both the header and IE syntax. You can do this manually or my command line. 

```
 touch app/views/layouts/_iesyntax.html.erb
 
 touch app/views/layouts/_header.html.erb
 
```

Then in go to your **app/views/layouts/_iesyntax.html.erb** file, you add the IE syntax

```html

<!--[if lt IE 9]>
  <script src="//cdnjs.cloudflare.com/ajax/libs/html5shiv/r29/html5.min.js">
  </script>
<![endif]-->


```
Next in you go to your **app/views/layouts/_header.html.erb** file, and add the header tag and its contents
```html
    <header class="navbar navbar-fixed-top navbar-inverse">
      <div class="container">
        <%= link_to "Rails Web Application", '#', id: "logo" %>
        <nav>
          <ul class="nav navbar-nav navbar-right">
            <li><%= link_to "Actionname1",   root_path %></li>
            <li><%= link_to "Actionname2",   action1_path %></li>
            <li><%= link_to "Contact", contact_path %></li>
          </ul>
        </nav>
      </div>
    </header>

```

This is the results from using partial for the **header tag** and **IE syntax**


```html
<!DOCTYPE html>
<html>
  <head>
    <title><%= full_title(yield(:title)) %></title>
    <%= stylesheet_link_tag 'application', media: 'all',
                                           'data-turbolinks-track' => true %>
    <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
    <%= csrf_meta_tags %>
    <%= render 'layouts/iesyntax' %>  
    <!--This is the render of the IE syntax-->
  </head>
  <body>
    <%= render 'layouts/header' %>
    <!--This is the render for the header-->
    <div class="container">
      <%= yield %>
    </div>
  </body>
</html>
```


Finally your done! You can add partials for other items as well. 




