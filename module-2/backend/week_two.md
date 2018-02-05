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

![Image of Schema](http://paulzaich.com/images/blog/sql-schema-example.png)

6. Define foreign key, primary key, and schema.
A foreign key is a field in one table that uniquely identifies an entry in another table. A primary key is a unique identifier for an entry in a table. A schema is a visual representation of the a table and the relations it shares with other tables.  

7. Describe the relationship between a foreign key on one table and a primary key on another table.
A table's foreign key is the primary key of another table. 

8. What are the parts of an HTTP response?
HTTP responses are composed of a status line, status code, response body, and response header. 

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
```ruby
# below returns all the values in the object associated with a certain key
Object.pluck(:key)

# below orders the object in an ascending fashion by the specified key
Object.order(:key)

#below finds the first instance of the Object where the key equals the desired result and if it does not exist it creates it
Object.where(key: "desired result).first_or_create

#below returns all merchants with invoices and the second method does the same where the 
#invoices's created_at date resides in a predetermined time_range

Merchant.joins(:invoices)
Merchant.joins(:invoices).where(invoices: {created_at: time_range}

#below translates an activerecored query to its equivalent statement in SQL
Merchant.joins(:invoices).to_sql

````
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
```bash
#below prepares the test database
rake db:test:prepare

#below reverts the database to the previous migration
rake db:rollback

#below runs the migrations
rake db:migrate
```
3. What two columns does `t.timestamps null: false` create in our database?
The `t.timepstamps null: false` stores a `created_at` and `updated_at` columns in the table.

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
A school has many teachers, and a teacher belongs to a school. 

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

6. Give an example of when you might want to store information besides ids on a join table.
It might be usefule to a description column. Or in the example of a doctor and many patients, it might be useful to store a presciption in the doctor_patient join table.

7. Describe and diagram the relationship between patients and doctors.
A patient has many doctors, and a doctor has many patients.

8. Describe and diagram the relationship between museums and original_paintings.
A museum has many original paintings and an original painting belongs to a museum.

9. What could you see in your code that would make you think you might want to create a partial?
Anytime a form submission is necessary for the Create/Update functionality, then a partial is a great way to keep code from repeating itself. 
