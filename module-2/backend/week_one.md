## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET - retrieve a resource from a url
  POST - create a new resource
  PUT - update an entire resource
  PATCH - update part of a resource
  DELETE - remove/destroy a resourece
2. What is Sinatra?
  Sinatra is a Domain-Specific Language written in Ruby that allows for easy CRUD functionality.
4. What is MVC?
  A model view controller setup architecture typically for web applications where separating the templates, database querying,   and servers is desired. 
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  In general, following coding conventions enables readabiliy within our code and in this case it further clarifies the point of the method in the controller. A post is sending data which will be used to query the database.
6. What types of variables are accessible in our view templates without explicitly passing them?
  Instance variables are acceccisble in our view templates.
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  ```ruby
  get '/horses' do
    @name = Mr. Ed
    erb :index
  end
  ```

9. What's the purpose of ERB?
  ERB allows for our template pages to be dynamic. Instance variable can be accessed and evaluted. This allows for the information stored in our attributes to be accesible to the user through HTML.
10. Why do I need a development AND test database?
 A test database allows for the isolation of fixture data from the real database.
11. What is CRUD and why is it important?
  CREATE, READ, UPDATE, and DELETE is important because it allows for direct server action corresponding to the five main verbs of HTTP. 
12. What does HTTP stand for? 
  HyperText Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <% Non-printing Ruby Method %> && <%= Ruby Values are Rendered ala string interpolation %>
14. What's an ORM?
  An object relational mapping is a way of translating database information into objects and is indifferent to how the file type of the database. 
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
17. What's a migration? 
18. When you create a migration, does it automatically modify your database?
    No, in order to modify the database, a user must run rake db:migrate.
19. How does a model relate to a database?
    A model ....
20. What is the difference between `#new` and `#create`?
  The ActiveRecord new generates an entry of a database but does not store it. To do that, a user must envoke the #save method. Create combines both #new and #save.

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film? 
```ruby
class CreateFilms < ActiveRecord:Migration[5.1]
  def change
    create_table :categories do |t|
      t.id            :integer
      t.title         :text
      t.desctiption   :text
      t.timestamps  null: false
    end
  end
end
```
  
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}
```
How would I add 'granola bar' to things you should have when hiking? First, I would add the additional three }}} marks to close the hash Then activites[:hiking][:supplies].push("granola")

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
