---
layout: post
title: ENG 612 Lab Report 3
---
### Data Cleaning: Before and After
The dataset we tackled for this lab was, on the surface, relatively uniform. Unfortunately, the more I looked at it, the more irregularities I noticed. I was hoping to construct a regular expression that would tackle most of my needs in one go, but I quickly realized that was not at all feasible. Below I have tracked the RegEx expressions and substitutions that I used to reach the clean dataset at the end. On the whole, this took me over two hours with many trials and errors.

**Beginning Dataset:**
>The Epoch Times, New York ed.; New York (NY)
>
>"La Voz Bilingüe"; Denver, Colo.
Jewish Advocate; Boston
>
Washington Informer; Washington, [D.C.]
>
News from Indian Country; Hayward,
WI.?
>
Afro - American, 5 Star edition; Baltimore, Md.
>
Diverse Issues in Higher Education; Fairfax Virginia
>
The Gay &amp; Lesbian Review Worldwide; Boston, MA
>
"The Hispanic Outlook in Higher Education; [Paramus N.J

**Regex:** “

**Result:** Removed all quotation marks (as shown in lab instructions)

**Regex:** [\(\),\?\.\[\]]

**Result:** Removed all special characters in the expression from the dataset
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver Colo
Jewish Advocate; Boston
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore Md
>
>Diverse Issues in Higher Education; Fairfax Virginia
>
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Denver [A-Za-z]{2,8})

**Substitution:** Denver CO

**Result:** Substituted all words after “Denver” between 2-8 letters (CO-Colorado) with “Denver CO”
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver CO
>
>Jewish Advocate; Boston
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore Md
>
>Diverse Issues in Higher Education; Fairfax Virginia
>
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Baltimore [A-Za-z]{2,8})

**Substitution:** Baltimore MD

**Result:** Substituted all words after “Baltimore” between 2-8 letters (Md-Maryland) with “Baltimore MD”
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver CO
>
>Jewish Advocate; Boston
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore MD
>
>Diverse Issues in Higher Education; Fairfax Virginia
>
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Fairfax [A-Za-z]{2,8})

**Substitution:** Fairfax VA

**Result:** Substituted all words after “Fairfax” between 2-8 letters (VA-Virginia) with “Fairfax VA”
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver CO
>
>Jewish Advocate; Boston
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore MD
>
>Diverse Issues in Higher Education; Fairfax VA
>
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Boston\n)

**Substitution:** Boston MA\n

**Result:** Substituted all instances of “Boston” followed by a new line with “Boston MA” followed by a new line.
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver CO
>
>Jewish Advocate; Boston MA
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore MD
>
>Diverse Issues in Higher Education; Fairfax VA
>
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (&amp;)

**Substitution:** &

**Result:** HTML coding for ampersand replaced with ampersand character
>The Epoch Times New York ed; New York NY
>
>La Voz Bilingüe; Denver CO
>
>Jewish Advocate; Boston MA
>
>Washington Informer; Washington DC
>
>News from Indian Country; Hayward WI
>
>Afro - American 5 Star edition; Baltimore MD
>
>Diverse Issues in Higher Education; Fairfax VA
>
>The Gay & Lesbian Review Worldwide; Boston MA
>
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** ;

**Substitution:** ,

**Result:** Semicolons replaced with commas
>The Epoch Times New York ed, New York NY
>
>La Voz Bilingüe, Denver CO
>
>Jewish Advocate, Boston MA
>
>Washington Informer, Washington DC
>
>News from Indian Country, Hayward WI
>
>Afro - American 5 Star edition, Baltimore MD
>
>Diverse Issues in Higher Education, Fairfax VA
>
>The Gay & Lesbian Review Worldwide, Boston MA
>
>The Hispanic Outlook in Higher Education, Paramus NJ

### A Reflection on Regular Expressions
The term "cleaning" was on my mind as I worked on this dataset. As Katie Rawson and Trevor Muñoz effectively argue against the term in "Against Cleaning," one particular statement in the article really captured my previous attitudes towards digital humanities: "When humanities scholars recoil at data-driven research, they are often responding to the reductiveness inherent in this form of scholarship" [^1] I admit that when I first started in DH I was highly skeptical of the value of some of these practices. I thought the entirety of the field was in the vein of what Rawson and Muñoz caution against in their article. I was skeptical of the notion of handing over intricate humanities work over to unnuanced computers. That data could possibly even be 'dirty' did not sit well with me. Is not every single scrap of information we can gain from humanities data valuable to someone, in some context? This experience "cleaning" data emphasized that while it is painstaking process, it is possible to maintain some of the humanity while working with data. Making sure to capture the nuance and to not write expressions that jeopardized information that might be useful to researchers seems to be possible. It took a lot of time and a lot of familiarity with the dataset to do so, but that extra effort is indeed worth it. Of course, even with our best efforts this is no guarantee. There were some unique aspects of the data that gave me pause (that wayward question mark that seemed to call into doubt the place of publication of Hayward, Wisconsin comes to mind), but ultimately I felt confident that though it took time, I was able to make the data processable but maintain its integrity. I actually credit some of my archival experience and learning to value original order in having a sort of instinct to not over clean, so to speak.

The transparency of being able to work through the cleaning process also kept me accountable in a sense. I wanted to make sure I could explain my choices to anyone who asked and that my decisions were well thought out. I thought about implementing regular expressions that could perhaps be used on a larger dataset in a similar vein. The expressions I wrote to normalize the city and state names could potentially be used in a larger dataset, taking into account various forms that information could take. While a larger dataset will likely contain even more variations that I could imagine in my wildest dreams, I aimed to think of a model that could be used by those that work with the same data in the future. I thought of the Data Sitter's Club as my model. Besides being an exciting (and delightful) exercise in nostalgia for me, that project is exemplary of an ideal collaborative, transparent project in the humanities. Down to sharing their email correspondence in ["DSC #2: Katia and the Phantom Corpus"](https://datasittersclub.github.io/site/dsc2.html) their transparency in their decision-making is really admirable. Though the reach of this particular post may not beyond ENG 612 at the University of Miami, documenting each step and each decision can help open up honest and fruitful conversations as we all learn these skills together to take into a larger DH sphere.

[^1]: Katie Rawson and Trevor Muñoz, “Against Cleaning,” from Debates in the Digital Humanities 2019 (2019)
