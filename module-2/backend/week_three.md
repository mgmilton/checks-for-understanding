## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
```
rails new project_name -T -d="postgresql" --skip-turbo --skip-spring
```
2. What do Models generally inherit from in rails?
```ruby
class Model < ApplicationRecord
end
```
3. What do Controllers generally inherit from in a rails project?
```ruby
class CoolController < ApplicationController
end
```
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
```ruby
resources :horse, only: :show
```
5. What rake task is useful when looking at routes, and what information does it give you?
```
rails routes
```
6. What is an example of a route helper? When would you use them?
```
object_path(@object)
```
Route helpers are userful to refer to a url path without specify the whole url.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
The `_url` is an absolute path whereas the `_path` is relative.

8. What are strong params and why are they necessary?
Strong params are a way of protecting against security threats by preventing arbritray assignment of attributes or the passing of attributes not associated with a certain model

9. What role does `form_for` play in helping us create our forms?
Form_for is a ruby method that allows for the creating and editing of multiple objects in a ruby form, which simplifies the html form process.

10. How does `form_for` know where to submit the user's input?
The form_for method takes an argument corresponding to the object that will be edited/created. 

11. Create a form using a `form_for` helper to create a new `Horse`. 
```ruby
<%= form_for @horse do |f| %>
   <%= f.label :name %>
   <%= f.text_field :name %>
   
   <%= f.submit %>
   <% end %>
```
12. Why do we want to validate our models?
This ensures that certain attributes are required for a data entry. Validations can also force model attributes to be unique.

13. What are the steps of the DNS lookup?
The DNS lookup starts with a query into the browser's local cache to see if it has the ip address associated with the domain name specified.  If there is no IP address there, it then looks in the router/local DNS server to see if other people have gone to this domain. If it can't find it there, it goes to to 13 root servers, then the TLD server, and then finally the authoritative name servers.


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
```ruby
def move
prance
end
```
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
```ruby
# for true
furniture[:table][:purchased]

# for 3
furniture[:table][:height]
```
16. What is inheritance?
Inheritance is the process by which a class takes on properties from another class. These properties can be methods, instance variables, or constants.
### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
