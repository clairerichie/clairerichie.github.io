---
layout: post
title: ENG 612 Lab Report 3
---

### Data Cleaning: Before and After
The dataset we tackled for this lab was, on the surface, relatively uniform. Unfortunately, the more I looked at it, the more irregularities I noticed. I was hoping to construct a regular expression that would tackle most of my needs in one go, but I quickly realized that was not at all feasible. Below I have tracked the RegEx expressions and substitutions that I used to reach the clean dataset at the end. On the whole, this took me over two hours with many trials and errors.

Beginning Dataset:
>The Epoch Times, New York ed.; New York (NY)
>"La Voz Bilingüe"; Denver, Colo.
Jewish Advocate; Boston
>Washington Informer; Washington, [D.C.]
>News from Indian Country; Hayward, WI.?
>Afro - American, 5 Star edition; Baltimore, Md.
>Diverse Issues in Higher Education; Fairfax Virginia
>The Gay &amp; Lesbian Review Worldwide; Boston, MA
>"The Hispanic Outlook in Higher Education; [Paramus N.J

**Regex:** “
**Result:** Removed all quotation marks (as shown in lab instructions)

**Regex:** [\(\),\?\.\[\]]
**Result:** Removed all special characters in the expression from the dataset
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver Colo
Jewish Advocate; Boston
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore Md
>Diverse Issues in Higher Education; Fairfax Virginia
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Denver [A-Za-z]{2,8})
**Substitution:** Denver CO
**Result:** Substituted all words after “Denver” between 2-8 letters (CO-Colorado) with “Denver CO”
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver CO
>Jewish Advocate; Boston
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore Md
>Diverse Issues in Higher Education; Fairfax Virginia
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Baltimore [A-Za-z]{2,8})
**Substitution:** Baltimore MD
**Result:** Substituted all words after “Baltimore” between 2-8 letters (Md-Maryland) with “Baltimore MD”
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver CO
>Jewish Advocate; Boston
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore MD
>Diverse Issues in Higher Education; Fairfax Virginia
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Fairfax [A-Za-z]{2,8})
**Substitution:** Fairfax VA
**Result:** Substituted all words after “Fairfax” between 2-8 letters (VA-Virginia) with “Fairfax VA”
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver CO
>Jewish Advocate; Boston
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore MD
>Diverse Issues in Higher Education; Fairfax VA
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (Boston\n)
**Substitution:** Boston MA\n
**Result:** Substituted all instances of “Boston” followed by a new line with “Boston MA” followed by a new line.
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver CO
>Jewish Advocate; Boston MA
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore MD
>Diverse Issues in Higher Education; Fairfax VA
>The Gay &amp; Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** (&amp;)
**Substitution:** &
**Result:** HTML coding for ampersand replaced with ampersand character
>The Epoch Times New York ed; New York NY
>La Voz Bilingüe; Denver CO
>Jewish Advocate; Boston MA
>Washington Informer; Washington DC
>News from Indian Country; Hayward WI
>Afro - American 5 Star edition; Baltimore MD
>Diverse Issues in Higher Education; Fairfax VA
>The Gay & Lesbian Review Worldwide; Boston MA
>The Hispanic Outlook in Higher Education; Paramus NJ

**Regex:** ;
**Substitution:** ,
**Result:** Semicolons replaced with commas

>The Epoch Times New York ed, New York NY
>La Voz Bilingüe, Denver CO
>Jewish Advocate, Boston MA
>Washington Informer, Washington DC
>News from Indian Country, Hayward WI
>Afro - American 5 Star edition, Baltimore MD
>Diverse Issues in Higher Education, Fairfax VA
>The Gay & Lesbian Review Worldwide, Boston MA
>The Hispanic Outlook in Higher Education, Paramus NJ
