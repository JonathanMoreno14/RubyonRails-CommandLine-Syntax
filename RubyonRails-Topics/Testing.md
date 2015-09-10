##Rails Testing
Testing is an important aspect for any Rails developer. With proper test-driven development (TDD) the Rails application can run smoothy with less chance of an error. Do not get me wrong there will be at times where you will find errors and will need to debug the application but with comman testing practices it will minimize the work needed for testing.

This link illustrates Michael Hartl's view on test-driven development (TDD) and when it is needed

 [*Box 3.3. When to test*](https://www.railstutorial.org/book/static_pages)


###Testing features

#####To run our test suite
```
bundle exec rake test

```
#####Method, that test the presence of an HTML tag

```
assert_select "HTML tag"

```

##Testing the Links layouts

Testing the links within the layout will be created by adding a new test file associated with ***integration test*** 

We begin by generating a template. The template can be called what ever you like. 
```
rails generate integration_test templatename

```
A new template is created within your  **test/integration/templatename_test.rb** This generates an appends **_test** to the name of the file.

Within your **templatename_test.rb** 

**test/integration/templatename_test.rb**

You can test the links of the layout by adding this code. We use the **assert_select method** for checking the links



```ruby

require 'test_helper'

class TemplateNameTest < ActionDispatch::IntegrationTest

  test "layout links" do
    get root_path
    assert_template 'ControllerName/Actionname1'
    assert_select "a[href=?]", root_path, count: 2
    assert_select "a[href=?]", action2_path
    assert_select "a[href=?]", contact_path
  end
end


```
We test the file by runnig the bundle command:

```

bundle exec rake test:integration


```
