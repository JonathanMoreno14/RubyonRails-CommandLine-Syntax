##Embedded Ruby

According to Rails Tutorial author Michael Hartl "*ERb is the primary template system for including dynamic content in web pages*." 

[Michael Hartl Rails Tutorial](https://www.railstutorial.org/)


#####Sample code from Rails Tutorial
This code illustrates the usage of ERb within an html document. 

```
<% provide(:title, "Home") %>

<title><%= yield(:title) %> | Ruby on Rails Tutorial Sample App</title>

```

**<% ... %>** is used by Rails to call the *provide* function and connect the string *home* with the *title* label. From there  we use **<%= ... %>** to place the *title* into the html by using Ruby's *yield* function. The difference between the both is not just the  **=** sign but also the distinction of each ones usage. As Michael Hartl points out; "*<% ... %> executes the code inside, while <%= ... %> executes it and inserts the result into the template*."



#####Embedding Code into the content of a webpage using Ruby
*yield* is used to embed content to a layout of a webpage
```
<%= yield %>
```
```html
<body>
    <%= yield %>
</body>

```

#####Stylesheet
**stylesheet_link_tag**

[Ruby on Rails API](http://api.rubyonrails.org/classes/ActionView/Helpers/AssetTagHelper.html) states that the tag "*Returns a stylesheet link tag for the sources specified as arguments. If you don't specify an extension, .css will be appended automatically. You can modify the link attributes by passing a hash as the last argument.*" 

```html
 <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track' => true %>

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

