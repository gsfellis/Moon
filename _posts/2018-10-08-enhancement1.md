---
layout: post
title:  "Task Scheduler"
date:   2018-10-08
excerpt: "Noob SNHUbot Enhancement 1: Task Scheduler."
tag:
- Noob SNHUbot
comments: false
---

Enhancement code can be found in the [feature_scheduler](https://github.com/gsfellis/noob_snhubot/tree/feature_scheduler) repository.

{% capture images %}
    {{ site.url }}/assets/img/task_scheduler_code1.png
    {{ site.url }}/assets/img/task_scheduler.png
    {{ site.url }}/assets/img/task_scheduler_code2.png
{% endcapture %}
{% include gallery images=images caption="Noob SNHUbot" cols=3 %}

---

## Table of Contents

[Introduction](#introduction)

[Improvements](#improvements)

[Reflection](#reflection)

[References](#references)

## Introduction
The originating artifact elected for enhancement for this and future milestones is a Slack chat bot called Noob SNHUbot, originally posted to GitHub on March 16, 2018 (noob_snhubot - Network, n.d.).  The project was an enrichment feature brought to the SNHU_coders Slack community I established to connect with other technology students enrolled at Southern New Hampshire University (SNHU).  In its simplest form, the chat bot simply responds to messages directed at it by members of the community, executes logic scripts and returns the output back to Slack.  Additionally, it’s the hope that other students can use the project to begin their own development journeys outside of the classroom, get familiar with GitHub and open sourced projects, and potentially create their first pull request.

There are several reasons I elected to include this in my portfolio, not the least of which is the enjoyment I’ve received working on this project.  Additionally, it’s a sizeable project with many opportunities for enhancement and written in a language that many consider easy to grasp.  This allows the project to achieve its intended goal of being a collaborative project to work on within a community.  Furthermore, a recent class, CS-340: Advanced Programming Concepts, allowed me to work in Python to create a RESTful API with a MongoDB backend, which I intend to bring to Noob SNHUbot.  This will allow me to demonstrate an ability to work in a full-stack environment, including the general software development and enhancements, the underlying database, an ability to work with third-party APIs, and an ability to engineer solutions using appropriate data structures and algorithms.

Lastly, a key factor for including this project in my portfolio is that it draws attention to the passion that I have for software engineering.  I thoroughly enjoy creating software and discussing its many facets and it’s in this vein I have created a coding community of over two-hundred members seeking to network with likeminded individuals.  Many students have come to get help with their homework assignments and have stuck around for the comradery the community creates.  In the age of online and distance learning the lack of connection with other students can not be understated, and this community does its part in bringing students together who otherwise may never have met silently earning their degrees online.

## Improvements
The first enhancement brought to the Noob SNHUbot project was to include a task scheduler.  The source code can be found in the feature_scheduler branch on the [GitHub repository](https://github.com/gsfellis/noob_snhubot/tree/feature_scheduler).  One of the features of the bot is to give students a way to check the Packt Publishing free book of the day, without having to open a web browser and go to the page.  This book is swapped out nightly at 8:00pm Eastern, and shortly after this time usually someone will ask the bot for it.  Adding a task scheduler was a logical next step, for this use case, since it’s a timed task the should easily be automated.

The improvement was created iteratively, starting in its simplest form automating the single task of displaying the free book at a specified time.  This was done by spawning a new thread within the program, housing a scheduler set to call an internal function within the bot at a specific time.  Once I could spawn a thread to perform the task, I created a method that could be used to spawn any of the internal bot commands for a given time.  To avoid conflicts, I also needed a way to keep track of the threads being spawned.  To address this, I needed to implement a data structure that would allow me to store information about the thread being spawned, so I used a Python dictionary, an implementation of a hash table (Mapping Types, n.d.).  I used the thread ID as the key in the dictionary, and then a subsequent dictionary containing values of various data needed to track, such as the actual thread object for active querying, the time the task was scheduled for, the name of the function to be called, and the arguments passed to it.  This allows me to query active threads for the existence of scheduled tasks, to avoid duplication, and ensure the threads have executed.  This also gives me an opportunity to implement a different data structure for this purpose and researching the best data structure for this may become part of a future milestone.

Beyond the initial enhancement plan, I also took the opportunity to add some new docstring comments to some methods, restructure the primary loop in the code and perform some additional cleanup.  While this had no effect on the programs ability to carry out its tasks, it has improved the maintainability of it.

## Reflection
Though there were some challenges to overcome in this project, I was able to successful implement a working feature into the bot from scratch.  Not only did it accomplish the mission I set out to achieve, but it added a framework for functionality that others can now leverage.  Any command can be scheduled to go off at a given time if desired, including future commands not yet written.  Perhaps there are other tasks or different websites that can be scraped to provide further resources for the community.  For these reasons, I was successful in implementing the planned enhancement, sticking mostly to plan.  In its current state it is what I would call “functional”, but there is still room for cleanup before the final submission into the portfolio.

I learned quite a few lessons during this small enhancement and ran into a few issues that I needed to work through.  The first challenge was simply how to spawn a separate process that would execute the command.  This is where previous knowledge of systems operations comes in to play and understanding about threads.  With that in mind I researched the Python documentation for how to spawn new threads, fortunately discovering the included threading module in the standard library.  The next crucial hurdle was having a task executed at a given time, which is where the sched module comes in to play.  Combining these two features together is the core solution for implementing the task scheduler inside the bot.  In researching for this task, it was difficult not to stumble across the many complicated facets of multithreaded programming like the Dining philosophers problem, a classic example of synchronization issues and ways to resolve them (Dijkstra, 1971).  Fortunately, this is a simplistic task, and there are no such resource conflicts to contend with, making it a great introduction to multithreaded programming, without weighing it down with complications.

At one point I was working on restructuring the code to make it a little more readable, I moved the primary loop logic from the global script scope into its own method.  Initial review and testing showed that this was perfectly fine.  I left the bot running to ensure the functionality of the scheduled task was working.  At 8:30pm, the bot kicked off its scheduled task and I rejoiced.  This was short lived, however, because shortly after other members tried calling additional bot commands, none of which were functioning.  What had occurred was that when I moved the logic from the global scope into its function scope, I did not include a very necessary global variable needed to identity the bot.  This forced me to review scopes and why this variable wasn’t being included.  Turns out, Python uses a slightly different global variable methodology I am not used to from experience in other languages and I had to explicitly call the global variable into the main() function scope to utilize it.  This was a great learning opportunity because scope is a critical element in all programming languages, and it’s good to brush up on the fundamentals.
The final challenge was that of keeping track of threads to not create duplicate tasks in the scheduler.  As I was building the functionality, it was quickly revealed that I would need to utilize some form of data structure to keep track of useful information for each task scheduled.  This was an early experience thinking through the selection of an appropriate data structure.  While I didn’t intend this to be a feature in the program, I found that it needed to be implemented.  I quickly put together a hash table to deal with the problem, but I’m uncertain if it’s the best data structure to use for this problem.  Because of my limited research and focus in this aspect, I have decided to focus on this data structure for the Data Structures and Algorithms enhancement.  Given enough time, I will do both this and the additional web scraping for the course catalog, but at this stage I think this will be an appropriate focus for next week’s milestone.
 
## References
Dijkstra, E. W. (1971, June). Hierarchical Ordening of Sequential Processes. Retrieved from University of Texas: [http://www.cs.utexas.edu/users/EWD/ewd03xx/EWD310.PDF](http://www.cs.utexas.edu/users/EWD/ewd03xx/EWD310.PDF)
Mapping Types. (n.d.). Retrieved from Python.org: [https://docs.python.org/3/library/stdtypes.html#typesmapping](https://docs.python.org/3/library/stdtypes.html#typesmapping)
noob_snhubot - Network. (n.d.). Retrieved from GitHub: [https://github.com/gsfellis/noob_snhubot/network](https://github.com/gsfellis/noob_snhubot/network)
