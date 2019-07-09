---
layout: post
title:      "Using JS to make a (mostly) one-page Rails app"
date:       2019-07-09 14:50:02 +0000
permalink:  using_js_to_make_a_mostly_one-page_rails_app
---


My latest project involves utilizing asynchronus Javascript object methods to change my multi-page Ruby on Rails app into a an app with all the same functionality that operates on only one page without refreshes. This is a modification of  my existing Rails app, the Freelance Tax Organizer( [click here for more info](https://mlmccor.github.io/rails_project_freelance_tax_organizer)).

So far the project has taken shape in the form of two pages: One is the main page, where the various tables of freelance income is displayed, the other is a page where all checks are sorted by employer, regardless of tax forms. On the main page, I've implemented the form to create new checks, which upon submission will remove the form, display the information about the new check, and add it to the appropriate table. I've also added the ability to display the information from each individual check( or each check's show page) to the main page. On the second page, I use Javascript to automatically make get request for the index of employers for the tax year ( the year of taxes you've selected). Upon clicking the name of an employer, the JS script makes a get request to the list of the checks for that employer and displays them in a table.

The biggest difficulty I ran into when creating this project was the idea of changing my existing Rails app to meet these requirements. I began to realize that every major web app goes through multiple revisions and added features to improve it. I'm very much a "if it aint broke don't fix it" type, but this forced me to think of ways I could improve my Rails app with JS to be more useful, and now I don't think I would want to go back. Strangely enough I still get a little sad when I think about all the Rails code that is now being bypassed because of the JS functions, but I know that all these changes make it more enjoyable to use.

My ideas upon expanding my current app include still adding the ability to track expenses for each year. Also be able to add all my Rails functions into my main page, making the app largely a single page app. Currently all delete functions and edit functions exist as other pages in my Rails app, but if I could bring all of those actions to the main page, the app would resemble a real app that people would want to use. 
