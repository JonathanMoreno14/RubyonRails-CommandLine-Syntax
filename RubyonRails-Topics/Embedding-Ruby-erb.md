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
