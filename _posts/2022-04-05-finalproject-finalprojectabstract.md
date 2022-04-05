---
layout: post
title: ENG 612 Final Project Abstract
---

**Team Members:** Claire Richie and Kate Albrecht

**Title of Dataset:** Early Modern Care

**Description of Dataset:**
Our data will contain bibliographic information of a carefully curated conceptual collection of entries from the English Short Title Catalog (ESTC) related to the act of caregiving. We will be using the date range of the ESTC (1472-1800) as the date range for our own dataset. We have begun collecting our data points by scraping the ESTC (ten entries at a time) using Zotero. Using a small corpus of women’s early print texts from the 1500s-1700s we have collected pivotal keywords the ESTC creators have attributed to this women’s writing. Then, we narrowed our keywords to a select list that contribute to our definition of Early Modern Care. For the purpose of this smaller, prototype dataset, we chosen 11 keywords that are scrapable in one setting (less than 200 datapoints each). Overall, we aim to scrape around 1000 texts under these 11 keywords for the purpose of this assignment. Choosing to scrape data already categorized by the ESTC makes our results more reproducible, as these categories are pre-defined by the catalog.

Why we have chosen these keywords as “Early Modern Care” is a little more nuanced. *Cura Personalis*, care of the whole person, body, mind, and spirit gives us boundaries to what we are including into our conception of care.  Moving beyond traditional professions and actions of caretaking, we have chosen keywords that focus on the emotions, networks, and relationships of care.  Ultimately, we would like to think about the household as a body and a body full of networks of care. In the early modern period, the body was intimately linked to its environment, its community, divinity, and its nourishment. By focusing on extended networks of caregiving and its practices, we can avoid imposing a modern, anachronistic, definition of care on these early modern texts. As we continue to refine this interlocking definition of care, we will create a comprehensive list of categories we will scrape the ESTC for.

**Metadata Fields:**

A. ESTC identification number: An identification number attached to each text when scraped from the ESTC.
B. Materiality of the text: The format of the text (most often “book”).
C. Author name: Name of the author or author(s) if applicable or known.
D. Full Title: The unabbreviated title of the original print text.
E. Publication Date: Date of publication (usually the year)
F. Page numbers:  The number of pages in a complete copy of the specific edition
G. Gender of Author: Male, female, or unknown–gender of the author(s)
H. Keyword Search from ESTC Subject headings: The main keyword used to scrape the datapoint
I. Shortened Title: The ESTC’s abbreviated title
J. Printer: The printer of the edition
K. Publication Place: Place of publication, most often London
L. URL of ESTC: ESTC URL
M. Subject Keywords as defined by ESTC: Sum of all keywords attached to the datapoint by ESTC creators (will need to be cleaned and regularized by regular expressions at a future date)

Further metadata fields will be added for the number of extant copies and the repositories at which these extant copies are housed. This will most likely need to be done manually depending on whether we can determine a scraping method (Python or other script) that would do this for us.

**Audience(s) for Dataset:**
- Early Modern scholars of book history
- Scholars of caretaking or the medical humanities more broadly
- Historians of the premodern periods
- Interested people who don’t know a lot about early print texts and want a smaller, more manageable dataset to explore (who may be intimidated by the ESTC and its sometimes fiddly interface) as well as a popular audience who may be casually interested in this topic.
- Educators and scholars of digital humanities who may want to work with a complete dataset
- Kate and Claire

**Questions for the Dataset**
- Roughly what percentage of surviving and cataloged texts from Early Modern England (1500-1800) were authored by women?
- What were women writing about and/or allowed to print about?
- How many editions of a particular text on caretaking survive and are cataloged?
- How are keywords overlapping across texts?  How can a certain text/edition/datapoint touch on different types of care?
- How did different definitions of caregiving interact and overlap with each other?
- What printers were publishing books on care?

**Related Projects:**
[Reading Early Medicine](https://reademed.mpiwg-berlin.mpg.de/)
[The Making and Knowing Project](https://www.makingandknowing.org/)
[Manuscript Cookbooks Survey](https://www.manuscriptcookbookssurvey.org/)

The Reading Early Medicine project is in some ways very similar to ours, especially in methodology. It also utilized the ESTC to create a database for texts on a certain topic in this case Early Modern medicine. We have modeled some of our methodology on this project, with some deviations. Our scraping approach is more standardized, as this project relied on keyword searches rather than utilizing the premade categories of the ESTC. This will hopefully make our project more reproducible. The content also differs. While there will be some overlap texts with Reading Early Medicine, we are not subscribing a to a strictly medical definition of care. Not all of Reading Early Medicine's texts will appear in our dataset, and we provide an expanded definition of medical and caregiving practice that also includes household and spiritual texts among others.

The two other projects related to ours I have selected are projects involving manuscripts, and they interact with our project in two different ways. The Making and Knowing Project is a project out of Columbia University that seeks to understand the material and practical reality of the recipes in one particular manuscript. Their resource has documented the detailed process as their team works through the practical application of each recipe, providing teaching resources, illustrations, documentation of the process, and a digital edition of the manuscript in question. While this differs from our methods, focusing on one text rather than taking a wide view of these kinds of texts, this project is related to ours through the practical measures of understanding caregiving. Essentially the other side of our project's coin, the Making and Knowing Project explores how texts of care might have actually been implemented on a personal level, while ours examines a larger culture surrounding networks of care.

The Manuscript Cookbooks Survey is an exciting project that attempts something similar to our dataset, except with manuscript recipe books. Their database contains the manuscript cookbooks produced prior to 1865 that are held at US repositories. It is searchable by institution, period, and keyword, allowing scholars to find exactly where these resources are held and understand the nature of these collections. This project has similar aims to ours in order to provide knowledge of different texts and where they are held, so scholars can utilize these resources and understand a more complex culture of manuscript recipe writing. Our project differs as we have cast a wider next with genre and are primarily focusing on print texts for the time being, but this database is also intimately connected with the culture of care we hope to capture with our dataset.
