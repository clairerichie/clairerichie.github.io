---
layout: post
title: ENG 612 Lab Report 5
---
### Answers to Lab 5 Questions
Question 1: This function has split the individual words in the string and separated them by commas, but it did the same thing to the "s" that was part of the contraction "let's." "\W" matches any character which is not a word character, which includes the apostrophe in contractions. "+" matches repetitions of the regular expression that proceeds it. So, as well as splitting the words separated by commas and spaces in the string, the regular expression also splits the contraction and treats it as two words.

Question 2: I used the chorus of Bruce Springsteen's "Dancing in the Dark" as my text:
>You can't start a fire
>You can't start a fire without a spark.
>This gun's for hire
>Even if we're just dancin' in the dark.

And the function returned the following: ['you', 'can', 't', 'start', 'a', 'fire', 'you', 'can', 't', 'start', 'a', 'fire', 'without', 'a', 'spark', 'this', 'gun', 's', 'for', 'hire', 'even', 'if', 'we', 're', 'just', 'dancin', 'in', 'the', 'dark', '']
I intentionally chose a string with a lot of non-word characters to see how it would break down, and it pretty much did what I expected. I now want to use my regular expression knowledge to write a function that would effectively preserve the syntax of the lyrics!

Question 3: The dataframe shows some pretty clear patterns that are also reflected in the graph of the entire dataset we looked at earlier. All but three of the text that use "virtu*" date from before 1650, and the results show that pretty overwhelmingly "virtu" and "vertu" are not used together, aside from the Erasmus text. Based on what we discussed in class, it makes sense that that text might contain Latin.

Question 4: The carat in the regular expression package matches the start of a string. So, it looks like this regular expression is looking for dates that begin with "20" which would match years of publication in the 2000's. It looks like that if the first date value lists a date from the 2000's (too modern to be on EEBO) this expression is telling the computer to include the second date value as well, which is hopefully the correct one.

### A Reflection on Working with Python
I admittedly came into this lab a little deflated from the bursting of my aspirational-Python-bubble after reading DSC [#12: The DSC and the New Programming Language](https://datasittersclub.github.io/site/dsc12.html). I had realized I was not going to be able to Duolingo my way to Python literacy with 15 minutes of practice each day, even with a digital humanist's version of a helpful green owl (i.e. a textbook.) I wanted to learn Python *in case* I eventually had a research question about a dataset that I could use Python to answer, but the DSC made it abundantly clear that learning bits of code to just have in my back pocket is not terribly feasible, especially given the time constraints of academic work. Just looking at the function and all of the tiny, specific, details of it made me feel intimidated, not because I did not think I *could* do it, but because I realized just how much time and brainpower it would take if I wanted to get to a level of comprehension of it.

That being said, I did get through it. It took reading it through a couple of times to understand what exactly each command was doing, and there was plenty of syntax I had to put in the "Google later" folder in my mind, but I felt confident that I basically understood how the function got from Point A to Point B in the most rudimentary fashion. Benjamin Schmidt's "Do Humanists Need to Understand Algorithms?" was helpful for perspective on this. While I did not fully understand the nuances of the code that was being run, I understood the transformations it was causing as it processed the data. Schmidt's argument that "a transformation expresses a coherent goal that can be understood independently of the algorithm that produces it" makes a lot of sense in this context.[^1]  The chart that was produced at the end of the lab makes sense without knowing exactly how we got there.

In theory, I know that as a humanities scholar I could probably 'get away with' not knowing every piece of Python known to man and machine. And that is no longer my goal. But I do want to learn enough that I am familiar enough with the process that I can look at a problem and visualize how to get to a solution via coding. Like I mentioned in my first post for this class, I want to have enough DH literacy that I can understand what went on behind my favorite projects. I want to understand what Python can do enough that I can look at my own projects and have an idea how to answer my research questions via Python. Schmidt's argument that no, humanists do not need to understand algorithms, makes sense in the context of this lab. However, I believe that humanists cannot go wrong by understanding the construction of codes, functions, and programs that produce the transformations we desire. So, I still want to learn Python. I just need a research question, a dataset, and some free time.

### Lab 6 dataset
The dataset I plan to work with for Lab 6 is from the [Reading Early Medicine](https://reademed.mpiwg-berlin.mpg.de/index.php/about-project) project. This project searched the English Short Title Catalogue (ESTC) for texts about health and healing and coded each title with information about title, genre, and information about the author. Their data is available for download as CSV files. I chose the category, "Remedies, multiple" because it was the largest dataset, containing over seven hundred entries. The project actually encourages others to download and work with their data and even includes links to data visualization tools like Voyant so users can create visualizations of their own with the REM data.

[^1]: Schmidt, Benjamin. "Do Humanists Need to Understand Algorithms?" *Debates in the Digital Humanities 2016*, https://dhdebates.gc.cuny.edu/read/untitled/section/557c453b-4abb-48ce-8c38-a77e24d3f0bd#ch48
