## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is a cookie?
A cookie is a unique identifier for a client that adds state to the HTTP process.

2. What’s the difference between a session and a cookie?
A session is piece of data larger than a cookie that is typically stored on the server and it details a user's history with a site (e.g. links clicked, items purchased, etc.). Additionally, cookies can be changed by a user but sessions cannot be.

3. What’s a flash and when do you want to use flashes?
A flash is a type of momentary session that lasts for a request and is then destroyed. Flash messages are useful for communicating to a user that an action has happened (e.g. a post was deleted, user successfully logged in, etc.)

4. Why do people say “HTTP is stateless”?
HTTP is statless because there is no infromation stored between clients and servers during the request response cycle.

5. What’s authentication? Explain.
Authentication is the process by which an application confirms a user is who they claim to be. This is most commonly applied through autheticating users through a username and password login.

6. What’s the difference between authentication and authorization?
Authentication determines that users are who they claim to be whereas authorization specified the fuctionality that is allowed for a type of user- admin vs. default user.

7. What’s a before filter?
A before filter requires that a method is executed before a new method is ran.

8. How do we keep track of a user once they’ve logged in?
A user is kept track through the use of a session.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
Namespacing allows for certain routes to be organized under other resources. This is useful that a certain action is allowed for only certain resources. For example, an edit feature migth only be accessed by admins and the url path with be something like admin/edit.

10. At a high level, what tools can you use to implement authorization? How would you use them?
Namespaced routes, enum's for defaulting users, helper methods like require_admin, and inheriting from the base controller. 

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
Definted at the model level, enum attributes map integers to values in an array, and these values are storedat the database level . 

12. What are some strategies you can use to keep your views DRY?
A few strategies for keeping views dry include utilizing partials, utilizing mixins, specifying variables in SASS, and having unique stylesheets for each section of a site. 

Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
holidays = [
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]

holidays.map do |holiday|
  holiday[:holiday][:name]
 end.sort.join(", ")

```  
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 
```
money.delete("$").to_i

```
