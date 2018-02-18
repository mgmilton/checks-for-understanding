## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is a cookie?
A cookie is a unique identifier for a client that adds state to the HTTP process.

2. What’s the difference between a session and a cookie?

3. What’s a flash and when do you want to use flashes?

4. Why do people say “HTTP is stateless”?

5. What’s authentication? Explain.

6. What’s the difference between authentication and authorization?
Authentication determines that users are who they claim to be whereas authorization specified the fuctionality that is allowed for a type of user- admin vs. default user.

7. What’s a before filter?
A before filter requires that a method is executed before a new method is ran.

8. How do we keep track of a user once they’ve logged in?
A user is kept track through the use of a session.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

10. At a high level, what tools can you use to implement authorization? How would you use them?

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

12. What are some strategies you can use to keep your views DRY?
A few strategies for keeping views dry include utilizing partials, utilizing mixins, specifying variables in SASS, and having unique stylesheets for each section of a site. 

Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 
