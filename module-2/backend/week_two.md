## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  I feel like ActiveRecord is an ORM that allows us to make powerful SQL requests without as much of the SQL syntax/jargon.
  Its a tool that lets us make connections between abstractions of data that we can treat as objects...objects that wouldn't
  have had a connection before and even give 'models' behaviors of these objects to do some really powerful things
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
  Through ActiveRecord we could call methods like Team.all, Team.find (or) Team.find_by_any_attribute_for_team
  We have a ton of ActiveRecord methods that we don't need to define in the Team class. I have access to them because of the
  inheritance that the given Team class has on ActiveRecord.


3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

  team4 = Team.find(4)
  team4.name

  team = Team.find(1) <- this gives us an easy variable to work with if we want to call .owner on the team with the id of 1.
  We could also be gross and chain methods {
    Team.find(1).owner
  }




4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

Team.find(4).owner
team4 = Team.find(4)
team4.owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

students belong_to teachers
teacher has_many students


6. Define foreign key, primary key, and schema.
  The primary key is the id in each table that is an abstraction of a real collection and it must always be unique. The primary key keeps track of each 'row' of a thing.

  Foreign keys are used as a connection from one table to another. A foreign keys context that I've seen the most often in my early career into databases have been one things primary key and another things relationship that we assign a key to.

  A schema represents a few things to me. The current state of each table I have, and also as a dangerous thing to touch but great to look at. The schema is also like a blueprint which really again, just points to the current state of each table.
  ALSO DONT TOUCH THE SCHEMA. Make a migration if you need to change something.


7. Describe the relationship between a foreign key on one table and a primary key on another table.
  I feel like I answered this in my definition, but to re-iterate...the foreign key of one table is the primary key of another.

    ex: Student will have a teacher_id...teacher has an id. The students teacher_id is the primary key of teacher thus teacher_id belonging to student is a 'foreign key' of that student.

8. What are the parts of an HTTP response?
  I don't remember all the parts off of the top of my head but I'll answer this to the best of my available knowledge, right here w/o looking.

      The header : Header will contain information like the status code from the server, any HTML / CSS as the view..that really all I can say. The request is far more interesting and I could tell you much more about that.

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
  that would be a one to many relationship. unless we are speaking about full time substitute teachers..there would be only one school to each teacher, many teachers to one school.
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
  forms in blogger...that was really nice. Also I could see nav bars, footers, general layout. being used in partials
