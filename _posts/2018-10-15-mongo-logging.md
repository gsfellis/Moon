---
layout: post
title:  "MongoDB Logging"
date:   2018-10-15
excerpt: "Noob SNHUbot Enhancement 3: Logging Slackbot Interactions with MongoDB."
tag:
- Noob SNHUbot
- milestone 4
- enhancement 3
- mongodb
comments: false
---

<center><a href="https://github.com/gsfellis/feature-logging" target="_blank" class="btn btn-success">View the Updated Source</a> <a href="{{ site.url }}/assets/submissions/noob_snhubot-feature_logging.zip" class="btn btn-warning">Get the Submitted Zip</a></center>

---

![MongoDB](https://webassets.mongodb.com/_com_assets/cms/MongoDB-Logo-5c3a7405a85675366beb3a5ec4c032348c390b3f142f5e6dddf1d78e2df5cb5c.png)

---

## Table of Contents

[Introduction](#introduction)

[Improvements](#improvements)

[Reflection](#reflection)

## Introduction

For this milestone I am continuing my work on the Noob SNHUbot project.  For this inclusion, I am leveraging a Python class I created in CS340: Advanced Programming Concepts.  The `MongoConnection` class handles working with a Mongo database including establishing the connection, changing the database and collection context, and performing Create, Read, Update, and Delete (CRUD) functionality.  This has now been included in the Noob SNHUbot project, with some slight alterations, that allows the bot to log its connections, received commands from users, and responses sent back to the Slack API.  The updated source code and SNHU submitted zip file are available by clicking the buttons above.

## Improvements

Previous versions of Noob SNHUbot used very crude print statements to output behaviors and reactions to various input.  When I run the bot on my server, I pipe this output to a file for review when needed, but ultimately is a poor implementation.  Additionally, when running the bot from my development environment, this output is only kept for the current working session.  I needed to include a way to keep this data persistent, and while a log file could be utilized, I thought it would be better to write these logs to a document based, NoSQL database.  

Having recently worked with MongoDB in CS340, this was the platform I was familiar with and knew would work well for the project.  When given the choice of what database platform to use, a lot of factors come in to play.  For me, I elected to use a NoSQL database for a few reasons.  Compared to SQL, the language used in MongoDB is JavaScript and in the form of JSON objects.  This made it easy to work with in Python because it's a one-to-one conversion for most JSON to the Python `dict`.  I didn't need to work in SQL in order to implement what I wanted, which gave a big advantage to MongoDB.  Additionally I wasn't entirely sure how I wanted my logs to be laid out.  This is a problem when using SQL because you have to define the schema before you start the implementation.  With Mongo, I could change the schema at will as I figured out how I wanted my logs to look.  Also I would come to use this flexibility to perform updates on received commands from users.  When a user triggers a command, that is first logged to the database, and when the bot makes a response I update the document with it.  If something goes wrong in between, I would be able to find the failed request by looking for commands without responses.  Lastly, and as previously mentioned, I had worked with the MongoDB interface in Python previously for CS340, so I was able to refactor some code for this project instead of starting from scratch.

I was able to drop the `MongoConnection` Python class I developed for the RESTful API project in CS340 into Noob SNHUbot and with a few key strokes I was writing documents to the Mongo database running on my home server.  As the project has grown in scope, I also decided this was a good time to clean up the folder and make it more manageable for future changes.  To do this, I moved the `Scheduler` class from the previous milestone, and `MongoConnection` into a new module called BotHelper.  I discuss this in further detail in my [Task Scheduler Update]({% post_url 2018-10-10-task-scheduler-update %}).  This allows me to separate tools and features that I may bring in to the project into a single module, cleaning up the root and better organizing the project.  So now to bring the `Scheduler` into the program, I must include `from BotHelper import Scheduler` in my import statements to bring it into scope, likewise for `MongoConnection`.

Lastly, to avoid having to hard code values, I decided it was a good time to bring in a configuration file into the mix.  I had previously saved the Slack client token in an environment variable on my server and workstation, but that was the only variable I needed to save outside of the program.  Now, I need to know which database server to connect to, which database and collection to write to, etc.  Using YAML, I created a configuration file which the program loads in if it exists, otherwise it falls back to the old method of using the environment variable and ignores all the calls to the database.  This also gives me a good platform to implement a way for scheduled tasks to be put into a configuration file, and not hard coded like they currently are.

## Reflection

This was an incredibly successful week, and my previous legwork in CS340 made this easy to implement.  This allowed me to catch up on some of the data structure and algorithm work I didn’t get completed in the previous milestone while also allowing me to clean up the project and add other functionality that I didn’t originally plan for, but which became apparent as I worked through the milestone.

This really demonstrates the importance of code refactoring and code reuse.  I was able to take something that I built for a RESTful API and mostly copy and paste it into a different project and make it work.  I corrected a few issues that didn’t function correctly, like switching databases and collections on the fly, but these were very minor changes.  This freed my time up to focus on overall functionality, creating the new module and implementing YAML configuration files which I’ve never worked with before.  Additionally, I was able to complete the SNHU Catalog Scraper I created in the previous milestone so that I could properly import the data into MongoDB.  Now I’m in a good position to fully implement the catalog into the bot utilizing the Hash Table data structure I came up with, which will be the focus for next weeks efforts.  Everything is now in place to fully implement all the enhancements I set out to, with some freedom to polish them beyond what I initially thought capable.
