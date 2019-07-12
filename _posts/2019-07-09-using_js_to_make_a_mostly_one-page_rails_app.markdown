---
layout: post
title:      "Using JS to make a (mostly) one-page Rails app"
date:       2019-07-09 10:50:04 -0400
permalink:  using_js_to_make_a_mostly_one-page_rails_app
---


My latest project involves utilizing asynchronus Javascript object methods to change my multi-page Ruby on Rails app into a an app with all the same functionality that operates on only one page without refreshes. This is a modification of  my existing Rails app, the Freelance Tax Organizer( [click here for more info](https://mlmccor.github.io/rails_project_freelance_tax_organizer)).

I've used JS to make my existing Rails app acheive most of it's functionality on one page. Instead of creating my tables for checks using Rails, I've made get requests to each TaxYear's employers and checks, creating an index of employers, and displaying their checks using a has_many relationship. I've also implemented the form to create new checks, which upon submission will remove the form, display the information about the new check, and add it to the appropriate table. I've also added the ability to display the information from each individual check( or each check's show page) to the main page. 

The biggest difficulty I ran into when creating this project was the idea of changing my existing Rails app to meet these requirements. I began to realize that every major web app goes through multiple revisions and added features to improve it. I'm very much a "if it aint broke don't fix it" type, but this forced me to think of ways I could improve my Rails app with JS to be more useful, and now I don't think I would want to go back. Strangely enough I still get a little sad when I think about all the Rails code that is now being bypassed because of the JS functions, but I know that all these changes make it more enjoyable to use.

My ideas upon expanding my current app include still adding the ability to track expenses for each year. Also be able to add all my Rails functions into my main page, making the app largely a single page app. Currently all delete functions and edit functions exist as other pages in my Rails app, but if I could bring all of those actions to the main page, the app would resemble a real app that people would want to use. 
