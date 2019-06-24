---
layout: post
title:  "Continued Education"
date:   2019-6-24 9:54:00 -0600
excerpt: "A table of progress being made in MOOCs, and other continuing education media."
tag:
- Continued Education
- Learning
- Excel
comments: false
---

<img src="https://cdn.pixabay.com/photo/2018/03/21/07/16/learning-3245793_960_720.jpg" alt="Learning" width="50%">

---
Here's a few things I've been working on, or meaning to learn.  Check back to keep up with my progress!  I currently have the Excel table ordered by `Progress`, but this is in no real order.

| # | Title | URL | Progress | Acclaim |
| ---: | --- | --- | --- | --- |
| 1 | C# Basics for Beginners | [Udemy](https://www.udemy.com/csharp-tutorial-for-beginners/ "Udemy") | 100% | [UC-YFS0VOJJ](https://www.udemy.com/certificate/UC-YFS0VOJJ/) |
| 2 | Spring and Spring Boot Fundamentals | [O'Reilly Learning](https://learning.oreilly.com/learning-paths/learning-path-spring/9781492055334/ "O'Reilly Learning") | 100% | []() |
| 3 | Python for Data Science and Machine Learning Bootcamp | [Udemy](https://www.udemy.com/python-for-data-science-and-machine-learning-bootcamp/learn/v4/overview "Udemy") | 61% | []() |
| 4 | Complete Python Bootcamp | [Udemy](https://www.udemy.com/complete-python-bootcamp/ "Udemy") | 45% | []() |
| 5 | Data Science A-Z | [Udemy](https://www.udemy.com/datascience/learn/v4/overview "Udemy") | 32% | []() |
| 6 | Java Programming Masterclass | [Udemy](https://www.udemy.com/java-the-complete-java-developer-course/ "Udemy") | 18% | []() |
| 7 | C# Intermediate: Classes, Interfaces and OOP | [Udemy](https://www.udemy.com/csharp-intermediate-classes-interfaces-and-oop/ "Udemy") | 0% | []() |
| 8 | C# Advanced Topics: Prepare for Technical Interviews | [Udemy](https://www.udemy.com/csharp-advanced/ "Udemy") | 0% | []() |
| 9 | Machine Learning A-Z | [Udemy](https://www.udemy.com/machinelearning/learn/v4/overview "Udemy") | 0% | []() |
| 10 | Deep Learning A-Z | [Udemy](https://www.udemy.com/deeplearning/learn/v4/overview "Udemy") | 0% | []() |
| 11 | Artificial Intelligence A-Z | [Udemy](https://www.udemy.com/artificial-intelligence-az/learn/v4/overview "Udemy") | 0% | []() |
| 12 | Learn C the Hard Way | [O'Reilly Learning](https://learning.oreilly.com/library/view/learn-c-the/9780133124385/ "O'Reilly Learning") | 0% | []() |
| 13 | The Rust Book | [Rust-Lang.Org](https://doc.rust-lang.org/book/title-page.html "Rust-Lang.Org") | 0% | []() |
| 14 | Complete C# Unity Developer 2D | [Udemy](https://www.udemy.com/unitycourse/learn/v4/overview "Udemy") | 0% | []() |
| 15 | Complete C# Unity Developer 3D | [Udemy](https://www.udemy.com/unitycourse2/learn/v4/overview "Udemy") | 0% | []() |
| 16 | RPG Core Combat Creator | [Udemy](https://www.udemy.com/unityrpg/learn/v4/overview "Udemy") | 0% | []() |
| 17 | Beginning C++ Game Programming | [Packtpub](https://www.packtpub.com/mapt/book/all_books/9781786466198 "Packtpub") | 0% | []() |
| 18 | The Unreal Engine Developer Course | [Udemy](https://www.udemy.com/unrealcourse/learn/v4/overview "Udemy") | 0% | []() |
| 19 | CS50 Introduction to Computer Science | [Edx](https://courses.edx.org/courses/course-v1:HarvardX+CS50+X/course/ "Edx") | 0% | []() |
| 20 | Free Code Camp | [Freecodecamp](https://www.freecodecamp.org/ "Freecodecamp") | 0% | []() |


---

Additionally, I extracted this table from an Excel spreadsheet I've been using to track my own progress.

Quite simply, I have a table created with some hyperlinks and percentages in it, and I've added a column that uses the `CONCAT()` Excel function to string together the various parts into the MarkDown text.

It's a bit archaic, but it does the job.

```excel
=CONCAT("| ", [@['#]], " | ", [@Task], " | [", [@Platform], "](", [@Link], " """, [@Platform], """) | ", TEXT([@[% Complete]], "0%"), " | [", [@Acclaim], "](", GetURL([@Acclaim]), ") |")
```
Produces a line like:

```text
| 1 | C# Basics for Beginners | [Udemy](https://www.udemy.com/csharp-tutorial-for-beginners/ "Udemy") | 100% | [UC-YFS0VOJJ](https://www.udemy.com/certificate/UC-YFS0VOJJ/) |
```

Which I can just copy and paste into this MarkDown file.  Additionally, to save, a column for no good reason, I created the `GetURL()` function, which extracts the URL text from a hyperlink in a given cell.

```vb
Function GetURL(rng As Range) As String
    On Error Resume Next
    GetURL = rng.Hyperlinks(1).Address
End Function
```

That's it for now.  Check back for more updates!