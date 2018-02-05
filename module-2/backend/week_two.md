## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is the most commonly used oject relational mapping tool for converting data from databases into Ruby Objects. This enables ActiveRecord's suite of methods that can sort, query, and access information from the database. 
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
```ruby
Team.all
Team.pluck(:key)
Team.order(:key)
Team.find_by
Team.find
Team.where
```

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
```ruby
Team.find(4)
Owner.find(Team.find(4).owner_id)
```


4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
```ruby
Team.find(4).owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram. 
The relationship will be a many to many. Students have many teachers. Teachers have many students. 

![Image of Schema] (http://paulzaich.com/images/blog/sql-schema-example.png)

6. Define foreign key, primary key, and schema.
A foreign key is a field in one table that uniquely identifies an entry in another table. A primary key is a unique identifier for an entry in a table. A schema is a visual representation of the a table and the relations it shares with other tables.  

7. Describe the relationship between a foreign key on one table and a primary key on another table.
A table's foreign key is the primary key of another table. 

8. What are the parts of an HTTP response?
HTTP responses are composed of a status line, status code, response body, and response header. 

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
