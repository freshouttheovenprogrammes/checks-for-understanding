## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
GET - use get to retrieve data
POST - use to edit something existing
PUT - use to create something new
DELETE - to delete
PATCH - use to update something
2. What is Sinatra?
Sinatra is a ruby lightweight framework
4. What is MVC?
Model, View, Controller.
  the model speaks to our database and holds the logical analysis
  methods that manipulate the data in the database as needed.

  the view holds the code that presents the abstraction to the
  viewer / user however we see fit.

  the controller routes all instruction to wherever necessary.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  Because Sinatra as a framework, relies on a specific file structure to be able to do the things we need it to do. (Ex: Public folder holds views.) This is important in linking spreadsheets and images, its important to know what Sinatra expects so we can give Sinatra what it needs to function.
6. What types of variables are accessible in our view templates without explicitly passing them?
  Instance variables
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  ```ruby
  get '/horses' do
    @count = 1
    @name = "Mr. Ed"
    erb :index
  end
  ```
8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
9. What's the purpose of ERB?
  Erb lets us do ruby things and have access to objects in our HTML code
10. Why do I need a development AND test database?
  Because we don't want to test the data as much as we want to test what happens when we want to manipulate it into something new, so this means that we will be creating data while we test that we want to keep separate from our sensitive data.
11. What is CRUD and why is it important?
  To me, I might be wrong (not referencing anything) but I feel like CRUD is the web equivalent of a low level Turing Test for a language to work. It basically means that we will be able to have functionality that lets us do everything basic into our objects through our ORM
12. What does HTTP stand for?
  Hypertext Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <% ruby code that doesn't display to the view %>
  <%= ruby code that displays to the view %>
14. What's an ORM?
  Object Relational Mapper. An amazing thing that allows us to represent data from one source into objects that we can create methods/functionality on and make a real abstraction of our data.
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

17. What's a migration?
  As best as I can explain, a migration is a multistep process in which first we must create, and then run. Migrations handle the blueprint, so to speak, of how we want to format our data. Migrations can handle all sorts of things! Migrations lets us change the attributes of different things that we will create objects to represent.
18. When you create a migration, does it automatically modify your database?
  No, you have to write code within the migration to modify the database.
19. How does a model relate to a database?
  A model speaks to the database and also relays information back to the controller.
20. What is the difference between `#new` and `#create`?
  I can't remember offhand and I'm trying to do this without looking. I think that while create lets us create in the database, new might be able to do something more, like pass in something that would normally not work (like a nil id?). The more I type this answer out the more I'm doubting mine!

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
    write the methods that ready the CSV in the seed, run iterative methods that find the pre-existing rows of information (id, title, description) and set the attributes of the rows to state of the object that now represents each column in the table. Code would look like

    films = CSV.readlines('filename', r), headers: true, header_converters: :symbol

    films.each do |film|
      Film.create(
                  id: row[:id],
                  title: row[:title],
                  description: row[:description]
                  )

22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores']
}
```
How would I add 'granola bar' to things you should have when hiking?

activities[:supplies] << 'granola bar'

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.

Encapsulation: Limiting or increasing scope of your methods and variables with intent.

Polymorphism: The thought that you can do one thing many different ways

Abstraction: Taking something specific and representing it in a 'high level' way.

Inheritance: A way to reuse methods or code from other existing objects.


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
  ^
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
  ^
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
