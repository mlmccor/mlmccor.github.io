---
layout: post
title:      "May the CLI Be With You"
date:       2018-12-19 19:25:08 +0000
permalink:  may_the_cli_be_with_you
---


For my CLI Project, I decided to go with something that spoke to my inner nerd-dom, the part of me that got me into coding in the first place. The program main focus is to display information about all of the named characters in the Star Wars movies.

Before I started coding, I started writing down the exact flow of my ideal CLI program. My program opens with options to list all the characters, list all the planets, list the films, and search for a specific character. Each list function brings up a numbered list of the desired option, where the user can type the number of an option to display more information about that character. Displaying a character will reveal their name, homeworld, species, and a list of Star Wars movies they've been seen in (due to the API I used not being up to date, you can only see data up to Episode 7: The Force Awakens). Selecting a planet will display its name, climate, terrain, and a list of characters who are natives of that planet. Selecting a film will display the title, director, release date, and the opening crawl featured at the beginning of the movie. Selecting a species will display the class and language they use, as well as example characters featured in the movies.

I started the project following the initial steps in Avi Flaumbaum's [CLI Gem Walkthrough](https://www.youtube.com/watch?v=_lDExWIhYKI) involving Bundler. After he reached the point where he created a CLI class, I began focusing on my own code and how I wanted to organize my methods/ classes.

I then focused on extracting the data. Since I used a public API, I was able to find an index page that showed the pure JSON data for the characters, planets, films, and species, and used the JSON library to parse the data into a readable hash in my code, instead of using the scraping method. 

After that, it was just managing data. I created CLI , API (instead of a scraper class), Character, Planet, Film, and Species class files, and used those to manage all the data.

My biggest issue while writing this program was overcoming certain formatting decisions of the source API. Instead of using the names of certain values (like a character's species or homeworld) the API instead placed a link to the full page of info for that value. My initial prototype redrew data from the API for each character, similar to the Music CLI, but that the program forced "scrape" 4 for times for each of the 87 characters (for the character, homeworld, list of films, and species). This program take a full 4 minutes at the least to start up (I think it took 10 during a Zoom call). I was urged by my technical coach to refactor it so that I drew all the data from the indexes of each of my classes to create my objects right at the beginning, then make the associations needed when the characters are created. This took it from 348 draws from the API to 25, speeding up my program a lot.
