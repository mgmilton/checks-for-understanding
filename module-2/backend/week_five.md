Questions from Week 5:
1. How do we make flash messages display on a page?
Inside the ```app/views/layout/application.html.erb```, we place the below message:

```ruby
    <main id="main-container">
      <% flash.each do |type, message| %>
      <%= content_tag :div, message, class: type %>
      <% end %>
      Cart: <%= @cart.total_count %>

    <%= yield %>
    </main>
  ```

2. Where is cart information/temporary information usually stored?
Cart information is stored within a session. 

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
Primarily for security reasons, a store would want to have purchase information of a cart in a separate database. Amazon also utilizes a cache storage system for their carts so that shoppers can consitently purchase books that they will not read. Thanks Jeff Bezos!

4. What is the purpose of the asset pipeline?
The purpose of the asset pipeline it reduce the storage load of all assets by compiling each photo and minify them into a serialized javascript file. This enables the application assets to be automatically combined with assets utilized by gems. 

5. Why do we precompile our assets?
We precompile our assets to compile and compress them into a single location.

6. What do each of the following tags do?
Stylesheet_link_tag loads all the stylsheets within the application, javascript_include_tag loads all the javascript files within the applicaiton, and image_tag "rails.png" loads the rails image. 

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
- Purpose/Abstract
- [Link Sectioning](#review-questions) for a table of contents
- Schema
- Local Installation
- Deployment
- Test Coverage
- Contributors
- Acknowledgements

8. What are the top four accessibility issues that we as developers should be aware of?
-1. An issue of web accessibility could be caused by a user having tacitle difficulties such as muscular dystrophy. 
-2. An issue of web accessibility could be caused by a user having learning disablity such as Fragile X disorder. 
-3. An issue of web accessibility could be caused by a user having visual impairment such as age related ocular degenartion.
-4. An issue of web accessibility could be caused by a user having hearing impairment suach as hypoplasia. 

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
Callbacks ```before_save``` should only be utilized in the controller. It is possible to find a ```before_save``` action in a Carts controller to add an update to a price. 

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method?
A scoped method refers to a function that can only operate on an instance of a model where an attribute equals a certain characteristic 
```
model Horse < ApplicationRecord
scope   scope :"Secretariat", -> { where(name: 'Secretariat') } do
    def print
      'a winning horse'
    end 
 ```
 A class method can operate on the whole model ``` self.minimum(:age)```. 

# Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

 - 12a. How would you add item with id of 48 with a quantity of 4?  
        ```
        cart[48] = 4
        ```
 - 12b. How would you increase the quantity of item 29?  
        ```
        cart.add_item("29")
        ```
 - 12c. How would you find out how many items your user is thinking about purchasing?
        ```
        cart.values.sum
        ```
  
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
A polymorphism - in the context of object oriented programming - means a subclass can override a method of a base class. Duck typing is the porcess of an object repsonding to a well-named method. For instance, the model horse could respond to a method nay where "I am horse is printed to the screen." Additionally a model station could respond to the maximum method where the argument is a numeric attribute of the model.
```ruby
horse.nay("string")
station.maximum(:id)
```

14. How would you clean the string "(630) 854-5483" to "630.854.5483"? 
 ```ruby
 stcharlesfox = "(630) 854 - 5483"
 stcharlesfox.gsub(/[()]/, "").gsub(/[ -]/, ".")
 ```

