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
