---
layout: post
title:  "Program Reflection"
date:   2018-10-21 23:02:00 +0500
excerpt: "Looking back on my time spent at SNHU."
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

## Collaboration and Communication

As an IT professional working in a project-based, team-oriented atmosphere, I’m often tasked with working with people of varying personalities and talents.  My experience at SNHU was no different in my interactions with other students and faculty.  In business I deal with customers and management, often having to explain very technical details with the non-technical, so I’ve developed a habit of breaking down complex technical details into easily to consume information.  I believe I’ve aptly demonstrated this in my time at SNHU through my many discussion post engagements with other students, as well as the papers I’ve written.

As an online student, however, I felt as though there wasn’t enough genuine collaboration and communication occurring, certainly not to the same degree students would get on campus.  It’s for this reason I created the SNHU Coders Slack community, to better engage with my fellow technical students and faculty members.  To date we’ve had over 250 members join, hovering between 70-100 active members per week, and we’ve sent over 150,000 messages to each other.  It has spawned two collaboration projects between members, including the Noob SNHUbot Slack bot, the focus of my portfolio, as well as a community run web page.  Many members have given and received help in understanding their homework assignments, and YouTube videos explaining programming concepts have been created to address common questions.  Overall, it’s been a great experience that addressed a need we weren’t getting as online students and I hope to see its use become more widespread at SNHU.

Having said all that, I believe my professional and academic experiences have prepared me well to effectively communicate and collaborate with people at all levels. I work and go to school remotely, so I leverage tools to help me effectively communicate through email, phone, Skype messaging, and now Slack.  I’ve been the project lead on many technical projects and know how to effectively deliver project details to stakeholders.

## Data Structures and Algorithms

Data Structures and Algorithms (CS260) was the comprehensive course on the topic at SNHU, utilizing C++ to dig deep into common structures for maintaining data, and algorithms to sort and manipulate the data within.  Once I formally studied the topic, subtle information hidden just below the surface of many programming languages became apparent.  For example, Python has the dictionary data structure, an implementation of a hash table, one of many of the data structures implemented in CS260.  While I was familiar with the concept of key-value pairs, I never knew how that feature was implemented, and now I’ve implemented one in both C++ and Python.  Likewise, my understanding of common data structures has vastly grown.  For example, I’m familiar with arrays and linked-lists, and have used them regularly and often interchangeably.  At the surface level, these two data structures function very similarly, but are quite different: arrays being contiguous allocated blocks of memory while linked-lists maintain a structure that holds data and points to related, disjointed blocks of memory (Parlante, 2001).  Knowing this allows a programmer to effectively decide on appropriate data structures for tasks.
	
Having worked in mostly higher-level languages, many of the day-to-day algorithms have been abstracted away.  Often when working in Python, C# or even C++, I don’t need to implement my own sort algorithms.  It’s usually built into the predefined data structures or is only a library call away.  However, studying the different algorithms to sort common data structures or implement binary search trees were eye opening.  It took my understanding of efficient coding to a new level and having a better understanding of time complexity to measure algorithm efficiency is a huge benefit.

While I may stick to using higher level languages that abstract away many of these low-level algorithms studying them alongside common data structures has given me a deeper understanding of the languages I have been using.  I have also gained a better understanding of how to gauge the efficiency of an algorithm and the tools to research problems in the future.
Databases

From my professional career I’ve been exposed to two major database infrastructures, including Microsoft SQL Server and MySQL.  I often troubleshoot issues with data, slow queries or indexes in both platforms, though this is purely from an administrative perspective.  Academically, however, I reviewed some data base technologies from the development side.  In Introduction to SQL, I reviewed many of the basics of writing queries for MySQL, but also dove deeper in to writing advanced queries with multiple advanced joins and aliasing.  

It was in Advanced Programming Concepts that opened my eyes to a whole new understanding of databases, the document based, NoSQL solution of MongoDB.   From the development side I immediately saw the benefit of using this type of structure because it allowed me to work with a common structure, familiar to any programming: the key-value pair.  It was more natural to think about my data in terms of data structures in code than relational tables in a database.  Both have their merits, but I can see the appeal to developers, not having to drop out of their language of choice to implement SQL statements.  The course leads up to creating a RESTful API with MongoDB backend, simulating a full-stack development environment.  Utilizing a relational database like MySQL would have slowed the development down, having to create the schemas and writing the SQL queries in a different language than the API implementation.

Having worked with both SQL and NoSQL databases professionally and academically, I feel confident in my ability to work with many persistent storage data platforms.

## Software Engineering

During my time in the IT and Computer Science programs, I learned a lot about many facets of software engineering.  Fundamentals in Information Technology (IT200) introduced me to the high-level technologies in general computing like web technologies, programming languages, and databases, while Foundations in Application Development (IT145) introduced me to the basic tasks involved in creating software applications in Java, as well as my first Integrated Development Environment (IDE), NetBeans.  Furthermore, IT145 was my first foray into object-oriented programming (OOP), learning crucial fundamentals in abstraction, encapsulation, inheritance, and polymorphism, the pillars of OOP (David, 2012).  My practice of OOP would continue throughout my time at SNHU in courses like Software Development with C#/.NET (IT230) and C++/.NET (IT312).  IT312 stands as one of my favorite experiences, where I learned and grew a lot as a programmer, being tasked with implementing a console dice game, from the ground up.  I elected to program Farkle, which I proudly display on my pinned repositories on GitHub (Fellis, 2017).  

IT145 introduced me to the Java programming language, which I had never worked with before.  While I can’t say I found any love for the language, I realized that I could quickly pick up new languages because I already understood many of the concepts from my own experiments in programming.  I was able to quickly navigate the documentation and reliably code solutions to what I was being tasked to do in any language put in front of me.  I ran the gamut of languages at SNHU, with Java, C#, C++, Python, and SQL, with a little JavaScript and HTML mixed in.  It has really laid the foundation for me to work in whichever programming language best suits the task or, more importantly, which ever technology stack the company or project I’m working for is utilizing.  Combining these experiences in different languages, combined with my knowledge of OOP has really prepared me to take on many tasks in software engineering.
Security

Regrettably, security was never a focus, nor interest of mine, either professionally or during my time at SNHU.  This isn’t for any reason other than my own, I simply believe that I don’t have the right mindset to be effective in the security field.  That’s not to say I don’t understand some of the basic principles that will help protect myself or my code in the future.  To me, the basics of security often come down to common sense.  Don’t share your passwords, change your passwords from time to time, don’t open emails from people you don’t know, things like that.  For programming, a recent example which I discuss in the portfolio is where I have a secure token given to me by the Slack team to connect my bot with.  I’ve put that in a configuration file, and I want to make sure that file never gets uploaded to my public GitHub repository, so others can’t utilize it to connect their own bots to the community.

I have much more experience in basic security from an IT administration perspective, such as locking down firewalls and enabling password policies on domains.  I’m certainly not a security expert, but I also don’t really plan to be.  I do wish to study up on secure coding to better understand how I can better protect the code I write and I’m sorry that I couldn’t able to squeeze in an elective like Secure Coding (CS405).  However, I do think that with my general knowledge of IT from professional and academic experiences that I have a broad understanding of what it takes to keep things secure in my future endeavors and look forward to exploring the topic further.

## References

David, K. J. (2012, September 2). Four Pillars of Object Oriented Programming. Retrieved from https://standardofnorms.wordpress.com/2012/09/02/4-pillars-of-object-oriented-programming/

Executive 8707 D. (2013, January 16). Retrieved from Packard Bell Club: http://pbclub.pwcsite.com/wiki/index.php/Executive_8707_D

Fellis, G. S. (2017, March 16). Farkle. Retrieved from GitHub: https://github.com/gsfellis/farkle

Free Learning - Free Programming eBooks. (n.d.). Retrieved from Packt Publishing: https://www.packtpub.com/packt/offers/free-learning/

Parlante, N. (2001). Linked List Basics. Retrieved from Stanford: http://cslibrary.stanford.edu/103/LinkedListBasics.pdf

Selenium. (n.d.). Retrieved from https://www.seleniumhq.org/
