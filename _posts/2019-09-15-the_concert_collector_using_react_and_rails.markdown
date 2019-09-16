---
layout: post
title:      "The Concert Collector, using React and Rails"
date:       2019-09-16 01:03:27 +0000
permalink:  the_concert_collector_using_react_and_rails
---


The *Concert Collector* is an a web application made to assist any avid concert concert attendee track the tours of their favorite artist and musical groups. The app allows a user to track up to date concert dates for their favorite artists and refine their collection to reflect their real calendar of concerts they intend to attend. Now, instead of poring through the user's music collection to remember their expanding list of favorite artists, looking for all of their tour dates, and copying any dates they have the possibility of attending, they can just visit this one app, search each artist one time, then be able to refine their summer concert list with a couple clicks.

**Sign Up**

Using the Devise Gem, I created two Rails views the app loads first, prompting the user to sign up or Login before they can have access to the main app.

**Searching an Artist and its concerts** 

A new user would then see a few blank fields and a search bar. This is the opening of the React portion of the app. The first React route (using the React-router-Dom) displays the Home Component, which contains the SearchBar, CurrentArtist, and the MyArtist components. A user would simply type a search query for a musical artist in the search field. The search query is sent the app's Ruby on Rails server running in the back end, which sends a fetch request to the Bandsintown API, which will return the closest match. The Rails API creates an Artist Ruby object with the data, then submits the data to the React client, where the the store updates with the appropriate data.
The artist data forces an update of the CurrentArtist component, where the musicians' name and image are displayed. That update causes the component to send another fetch request to the Rails API, this time sending a fetch request to Bandsintown API for that artist's list of confirmed concert dates. That list of dates is then displayed on the page. With each concert, a button is added to add that concert date to the user's "collection." When the add button is clicked, the concert is sent to the server database where the Ruby object is created, associated with the user, and stored.

**The My Artist Component **

After every use of the SearchBar component, the resulting artist is added to that user's list of artists. This list is displayed in the My Artist section of the page. This list is used so that the user can just click the name of the artist and that artist becomes the new CurrentArtist, where the artist's current list of concerts is again fetched from the API so it is up to date. This part of the app makes it easy to keep track of their favorite artists, because they never have to type those names in the search bar after the first time.

**Accessing a user's collection** 

When a user wants to access their collected list of concerts, they can click on the My Concerts link in the overhead nav bar. Doing so will use React Router to Display the MyConcerts component, which displays a list of the user's saved concerts from the CurrentArtist component. Since concerts are saved in the database, the user can refresh and the list of concerts will still stay intact. Each concert listed as a link with the full date and city, state (where applicable) and country.

**Concert Component**

The link on each concert uses React Router to display the MyConcert component which displays details about the selected component. These details include artist, date, time, venue name, venue city, state, and country. If the concert has an announced date that tickets go on sale, that will be displayed as well.

That's it for the *Concert Collector*! My first planned updates for the app will be to sync with the user's Google calendar, or other calendar application, and automatically add the user's concerts to that calendar. Also I will implimenting a way to sort past concerts away from the upcoming ones, so the user still reflect on past concerts without getting in the way. Thanks for reading!
