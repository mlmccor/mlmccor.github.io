---
layout: post
title:      "Sinatra Project: Game Library and Progress Tracker"
date:       2019-03-16 13:02:38 +0000
permalink:  sinatra_project_game_library_and_progress_tracker
---


I just finished my first project using Sinatra and ActiveRecord! It's function is to allow a user to add in their own library of video games, then be able to create custom status messages for themselves to mark their progress throughout the game. They can also look up info about any game in the database (in case they're looking for more games to purchase) and look at other users' pages to see their progress in their games. My database entries utilized a User table, Game table, and a UserGame join table. 

Instead of having the users create the entries for the games, I used an API for an [International Game Database](https://api.igdb.com/) to populate my games database with the 50 most popular games with a high critic rating (50 is the max I can get with my current API key). This gave me access to the game title, short summary of the game, and a url to the game's entry at the IGDB's website. Because of this, I decided not to add the ability for users to create game entries.  

The most interesting problem I had to overcome actually had to do with the database itself.  I wanted the user to be able to keep track of their own game library, as well as the progress status of each game. Since the status had to be individual to the game **and** the user, I couldn't do what most of the lessons in Learn do, and have the status be a column in the game database. I decided that it made the most sense to actually have the user be able to keep track of the UserGame entries, instead of their associated Games. By putting a status column in the UserGame table, and having the User keep track of those on their homepage, it would allow two users to have different statuses for the same game.

Another interesting feature of my app is that, I wanted my app to mimic social media platforms and be able to visit other peoples home page to see what games they were playing. This meant I couldn't lock the home pages to only allow access to the user of that home page, like we did in many of Flatiron's lessons, but I still needed a way to keep other users from changing my account info, library, or status data. So instead of checking for the current user in the controller action (then redirecting the page if the current user was not that user's page), I decided to put that conditional logic in the view page rendoring itself. If the current user was not the user who's page was being loaded, it simply would not load the code for the links for editing account info, or changing the statuses of games, or the delete button. This would allow users to safely have other users visit their profile page, without worry about others changing anything they weren't supposed to. 

Thanks for reading about my Sinatra Project!
