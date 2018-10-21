---
layout: post
title:  "Portfolio Summary"
date:   2018-10-21 23:10:00 +0500
excerpt: "A summary of the contents of my portfolio for CS499."
tag:
- Professional Self-Assessment
- about
- CS499
comments: false
---

## Professional Self-Assessment Posts

Part 1 - [My Journey]({% post_url 2018-10-21-my-journey %}).

Part 2 - [Program Reflection]({% post_url 2018-10-21-program-reflection %})

Part 3 - [Portfolio Summary]({% post_url 2018-10-21-portfolio-summary %})

---

## Portfolio Summary

I was able to bring the three portfolio artifacts: software design and engineering, data structures and algorithms, and databases, into one project, Noob SNHUbot, the Slack chatbot created for the SNHU Coders community previously mentioned.  What started out as a simple curiosity to explore a technology I hadn’t used before, has flourished into a full project.  While the bot was working before starting these artifact enhancements, I believe the new changes have laid the foundation for a project that is fun, engaging, and has potential for being highly collaborative.  As mentioned we’ve had another student begin contributions to it, making changes and fixing bugs that I had not addressed, so that is very exciting for me to see.

The first artifact I brought to the project under the category of software design and engineering, was a multithreaded task scheduler.  There was one very specific use case in mind when I thought of creating this, but I wanted to code it in such a way that others might be able to use it as a spring board for other ideas.  At 8:00PM Eastern time, the Packt Publishing free book of the day changes (Free Learning - Free Programming eBooks).  I had already created a command module in the bot where users could request the book information, scraping the web page on demand and presenting it in Slack.  With the task scheduler in place, the bot now programmatically sends this data to the #book-club channel on our community at 8:30PM.  Once the task kicks off, it removes the it from the queue and schedules it again for the next day.  Again, this is a very specific use case, but it could easily be leveraged to send a message out on Thursdays and Sundays reminding undergraduate students that their SNHU homework is due.  This is not a perfect implementation, and there’s a few enhancements I need to bring to it.  For one, the task is coded into the bot code itself, which is fine for one task, but it’s not easy to implement another.  I want to move this to YAML configurations, which I introduced to the bot in a later artifact.  Additionally, the scheduling is a bit inflexible, currently only working for a given time, not specific dates.  So, it can’t be used to schedule a task to run once, or to effectively set up a schedule like Thursdays and Sundays, or the first day of every week, so this is something I’d like to improve in the future.

The second artifact I introduced was a two-part effort.  The first was to perform some extract-transform-load (ETL) operations to gather data from the SNHU Course Catalog web page.  This was not easy but was a great exercise in a new tool that I hadn’t used before, Selenium.  Selenium “automates browsers” (Selenium), which I used to work through the process of browsing the catalog for every category, and extracting data from the pages into JSON format, which I later stored in a Mongo database.  This was all so that I could demonstrate an ability to develop, or at the very least implement, an appropriate data structure to implement this data into the bot.  Where this data is essentially a key-value reference, it’s well suited to the Python dictionary, but I opted to implement my own version of a Hash Table, leveraging work from CS260 and porting it from C++ to Python.  The first week I spent developing the tools to scrape the data and test the Hash Table implementation with it.  It wasn’t until I completed the final artifact, the Mongo database, where I implemented both the data and the structure into the bot.

For the final artifact I wanted to implement a database which I could use to record and review logs.  The bot has a hard time staying connected to the Slack Real-Time Messaging API, so I wanted to trap these somewhere I could study them for any kind of patterns.  Additionally, because I’m not on Slack all the time, I wanted a way to see if users were interacting with the bot.  Having just completed the RESTful API in CS340, I had created a wrapper class around PyMongo to handle Mongo database CRUD operations.  I was able to drop this class directly into Noob SNHUbot with very little modification, only correcting things I overlooked in its original implementation.  Then I could create the program changes to begin logging to the database.  When it was complete, I was logging connections and reconnections to one database, and user interactions and bot responses to another.  Because this went so smoothly, I also implemented the data from the previous artifact into its own database, to later be leveraged in a new bot command.	
