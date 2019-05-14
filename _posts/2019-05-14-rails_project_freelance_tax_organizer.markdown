---
layout: post
title:      "Rails Project: Freelance Tax Organizer"
date:       2019-05-14 13:37:58 +0000
permalink:  rails_project_freelance_tax_organizer
---


There's a lot of things I love about being a freelance musician. You get to work the hours you want, in some cases charge the price you want, and you get to pocket all the money. Unfortunately, filing your taxes are a little more complicated than our friends who are employees of companies. 

Here's a little refresher on income types for those who are lost. Anyone who is an employee of a company files/receives a Form W-2 with their earnings, because their employer is counting them as an employee and taking out taxes from their pay before they receive it. Freelancers are hired by companies as contractors, which means they are hired on a temporary basis and aren't counted as employees. Freelancers instead receive a  Form 1099 MISC from this employer, as well as their full check, of which the freelancer will pay taxes on when they file their taxes in the spring. Because of this, the IRS treats the freelancer as the "owner of a business," requiring the freelancer to keep records of all revelent payments, and relevent expenses in order to keep from losing a third of your annual income filing taxes. For info on this subject, check out [this great article](https://turbotax.intuit.com/tax-tips/irs-tax-forms/the-difference-between-a-1099-and-a-w-2-tax-form/L8drkTeTQ) on the difference between these two tax forms.

Because I am not a very organized person in general ( you should see my desk right now ), filing freelance taxes myself is a long, annoying process, usually involving me digging through bank statements, my calendar, and having Google Maps open to figure out my mileage driven. This is what gave me the idea of my Ruby on Rails app, a web app that will display all the information a freelancer needs in order to file their taxes as easily as their friends sporting W-2's. 

After the user creates an account with a username, email, and password, they are prompted to choose the year they would like to view. In the future, this will have all the user's previous years tax records since the user created the account. After choosing the year, the user simply adds any check info the have received, with the relevant info. At the end of the year, the year home page will organize all income organized in a Form 1099 MISC in separate tables with their total amounts and mileage, and a table at the bottom of the page with any income that is not covered by a Form 1099 MISC with those totals. 


In the future I hope to add an expense tracking feature, functioning similarly to the income. The user will be able to add expenses in different categories, and the app calculate totals for the separate categories. I would like the end result to be one page with all the information a freelancer needs to file their taxes.

For anyone currently working on any project, my first suggestion is to come up with as complete an idea as you can before working. Be able to mentally have a plan for each page. Then, using that idea, figure out your tables. Think about what relations you need in order to display the data you want. Then begin writing your migrations and controllers. Planning this much in advance will save you a lot of time.

Thanks for taking the time for reading this and happy coding!!

