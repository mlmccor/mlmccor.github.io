---
layout: post
title:      "Sanitizing your SQL data in forms"
date:       2019-01-15 15:25:48 +0000
permalink:  sanitizing_your_sql_data_in_forms
---


As Rubyists, we tend to rely on the all-powerful String Interpolation operator to plug our many variables into Strings...

```
def say_hello(name)
  "Hello #{name}!"
end

say_hello("Dave")

"Hello Dave!"
```

This disciplined habit has to be put to the side when dealing with SQL queries. Let's say you have a list of student objects:

```
class Students
  
  attr_accessor :name, :age

  @all = []

  def initialize(name, age)
    self.name = name
    self.age = age
    self.class.all << self
  end
  
  def self.all
    @all
  end
end
```

And wanted to write a method to add all of your collected students to a table in a database:

```
def self.add_to_table
 self.all.each do |student_data|
  "INSERT INTO students (name, grade) VALUES (#{student_data.name}, #{student_data.grade}"
 end
end
```

Best case scenario, something like this gives you an error that it has no idea what `#` is. At worst, it can leave you open to hackers who want to take advantage of vulnerabilities like this ( see [SQL Injection](https://en.wikipedia.org/wiki/SQL_injection) ).

#### Using Bound Parameters

The Execute statement will allow you to pass the variables you want inserted into the table into the VALUES section of your query. 

```
def self.add_to_table(database)
 self.all.each do |student_data|
  database.execute("INSERT INTO students(name, grade) VALUES (?, ?)", [student_data.name, student_data.grade])
 end
end
```

This will sort the appropriate variables into the appropriate column without messing with the problems of string interpolation. Another advantage to using this is that if you had a filter for valid names a grades, this command will accurately compare those instance variables to those filters. 


