## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

rails new projectname -T -d=postgres

I don't remember the syntax for skipping Spring or Turbolinks
I'd actually like to learn more about those things if we have time.

2. What do Models generally inherit from in rails?

ApplicationRecord

3. What do Controllers generally inherit from in a rails project?

ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

resources :horses, only: [:show]


5. What rake task is useful when looking at routes, and what information does it give you?

rake routes

Prefix | Verb | URI | Action

6. What is an example of a route helper? When would you use them?

horse_path(horse) = show me THAT horse
horses_path = All the horses
edit_horse_path(horse) = Lets change this horse!
new_horse_path = We need a new horse!

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

I have no idea! I haven't used that yet and will check it out after this CFU

8. What are strong params and why are they necessary?

This is something I'm not 100% on and will check after the CFU but, I really want to show you all (i typed guys :-\ ) where I'm truly at and strong params are something I want to understand better anyways so, here goes....

Strong params are used when we need to create a new 'thing'. They have syntax like params.require(:thing).permit(:attr1, :attr2, etc). What this does and means...is that we don't get items in our database that don't have all the necessary columns filled out for each row of our things. Maybe there are some optional attributes but for the most part, we need all the things. Strong params also keep security tight on our application.

9. What role does `form_for` play in helping us create our forms?

form for builds out the HTML and CSS for basic forms, as well as being 'smart' and knowing what model we are referencing (which is pretty awesome but can be sometimes like 'you know too much and I wish I could tell you exactly what I want') form_fors then have a submit feature which passes that data back to the controller and then do different things like save to the DB or whatever we need it to do.

10. How does `form_for` know where to submit the user's input?

Based on the file structure

app
  ¬ views
   ¬ model
    ¬ action.html.erb

it knows its in the view so, it hits the action and the file structure tells it 'hey this will affect 'this' model so I must make a submit that matches that.'      

11. Create a form using a `form_for` helper to create a new `Horse`.

<% form_for @horse do |f| %>
<%= f.label :name %>
<%= f.text_area :name %>

<%= f.label :attribute %>
<%= f.text_area :attribute %>

<%= f.label :other_thing %>
<%= f.text_area :other_thing %>

<%= f.submit %>

<% end %>



12. Why do we want to validate our models?

To make sure that we have all inforamation per row per column of this or that object
